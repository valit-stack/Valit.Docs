=====================
Validation strategies
=====================
Different business logic require different validation strategies. Sometimes it might be necessary to validate the entire model when in other cases you might need only information that model has at least one property which does not fulfil the condition. Because of that, Valit offers three different behaviours for your validation process:

- Complete strategy (default)
- Fail fast startegy
- Custom strategy

All of the above can be activated using ``WithStrategy()`` extension on your ``ValitRules`` object.

Complete strategy
------------------
Complete strategy is a default one for Valit. That's why it's not required to define it's explicitly in your code. The strategy simply makes your model validated entirely. Here's an example:

.. sourcecode:: csharp

    public class RegisterModel
    {
        public string Email { get; set; }        
        public int Age { get; set; }
    }   

    void ValidateModel(RegisterModel model)
    {
        IValitResult result = ValitRules<RegisterModel>
            .Create()
            .WithStrategy(strategyPicker => strategyPicker.Complete) // not required
            .Ensure(m => m.Email, _=>_
                .Required()
                    .WithMessage("Email is required")
                .Email()
                    .WithMessage("Email is incorrect"))
            .For(model)
            .Validate();

        if(!result.Succeeded)
        {
	    foreach(var message in result.ErrorMessages)
	    {
		Console.WriteLine(message); // prints both messages
	    }
	}
    }

As mentioned, because Complete strategy is a **default one** it is not required to define it explicitly.

Fail fast strategy
------------------
Fail fast strategy is handy when you only care about the overall result (so does the validation succeeded or not). In this mode, your validation process runs until first error is reached. The example below present described strategy:

.. sourcecode:: csharp

    public class RegisterModel
    {
        public string Email { get; set; }        
        public int Age { get; set; }
    } 

    void ValidateModel(RegisterModel model)
    {
        IValitResult result = ValitRules<RegisterModel>
            .Create()
            .WithStrategy(strategyPicker => strategyPicker.FailFast)
            .Ensure(m => m.Email, _=>_
                .Required()
                    .WithMessage("Email is required")
                .Email()
                    .WithMessage("Email is incorrect"))
            .For(model)
            .Validate();

        if(!result.Succeeded)
        {
            foreach(var message in result.ErrorMessages)
            {
                Console.WriteLine(message); // prints only Required message
            }
        }        
    }

In the example above, the ``ErrorMessages`` contains only one error message added to the ``Required()`` rule. Since this one is not fulfilled, Fail Fast strategy stops the validation process right after that. 

Custom strategy
------------------
Of course, both Complete and Fail Fast strategies are the ones we consider as the most useful. But if they still are not enough for your needs, your can create custom strategy as well. The whole process is straightforward:

1. Create a class which implements ``IValitStrategy`` interface
2. Put "failing logic" inside ``Fail()`` method
3. Put logic on validation completion inside ``Done()`` method
4. Pass the instance of your custom strategy inside ``WithStrategy()`` extension

Let's say that our validation strategy should stop the whole process after third unfulfilled rule. The example implementation might look as follows:

.. sourcecode:: csharp

    public class RegisterModel
    {
        public string Email { get; set; }        
        public int Age { get; set; }
    }

    public class MyCustomStrategy : IValitStrategy
    {
        private int _failCounter;
	
        public void Fail<TObject>(IValitRule<TObject> rule, IValitResult result, out bool cancel) where TObject : class
	{
	    if(! result.Succeeded)
            {
                _failCounter++;
            }

            cancel = _failCounter >= 3;
	}

	public void Done(IValitResult result)
	{
            var message = result.Succeeded? "We did it!" : "We failed!";
	    Console.WriteLine(message);
	}
    }

    void ValidateModel(RegisterModel model)
    {
        IValitResult result = ValitRules<RegisterModel>
            .Create()
            .WithStrategy(new MyCustomStrategy())
            .Ensure(m => m.Email, _=>_
                .Required()
                    .WithMessage("Email is required")
                .Email()
                    .WithMessage("Email is incorrect"))
            .Ensure(m => m.Age, _=>_
                .IsGreaterThan(16)
                    .WithMessage("Age must be greater than 16")
                .IsLessThan(50)
                    .WithMessage("Age must be less than 50"))
            .For(model)
            .Validate();

        if(!result.Succeeded)
        {
            foreach(var message in result.ErrorMessages)
            {
                Console.WriteLine(message); // Doesn't print last message
            }
        }        
    }
