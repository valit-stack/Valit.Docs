=====================
Validation errors
=====================
Having a validation result (so succeeded or failed) is fine but in most cases we want to provide more details to the end-user or other parts of the system. Valit provides two different mechanisms for such a thing:

- error messages
- error codes


Error messages
------------------
In order to add an error message to the specific validation rule use ``WithMessage()`` extension. All messages are stored inside ``ErrorMessages`` property in the ``IValitResult`` object. The example below present the usage of error messages:

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
            .Ensure(m => m.Email, _=>_
                .Required()
                    .WithMessage("Email is required")
                .Email()
                    .WithMessage("Email is incorrect"))
            .For(model)
            .Validate();

        foreach(var message in result.ErrorMessages)
        {
            Console.WriteLine(message);
        }
    }

Message provider
------------------
The above example is cool but it has one disadvantage - all messages are hardcoded. Of course it's nothing really bad for a small projects but in a typical scenario you typically store that kind of data somewhere else like database. That's why besides error messages Valit supports also **message providers**. The usage is fairly simple:

1. Create a class which implements generic interface ``IValitMessageProvider<TKey>``. This interface provides one method called ``GetByKey(TKey key)``.
2. Pass the instance of your provider to ``ValitRules`` using ``WithMessageProvider()`` extension.
3. Use ``WithMessageKey()`` extension on each rule you want to extend with custom message.

Here's an example:

.. sourcecode:: csharp


    public class RegisterModel
    {
        public string Email { get; set; }        
        public int Age { get; set; }
    } 

	public class MyMessageProvider : IValitMessageProvider<string>
	{
        private readonly IReadOnlyDictionary<string, string> _messages = new Dictionary<string, string>
        {
            { "Key1", "Email is required" },
            { "Key2", "Email is incorrect" },
        };

		public string GetByKey(string key)
            => _messages[key]; 
	}

    void ValidateModel(RegisterModel model)
    {
        IValitResult result = ValitRules<RegisterModel>
            .Create()
            .WithMessageProvider(new MyMessageProvider())
            .Ensure(m => m.Email, _=>_
                .Required()
                    .WithMessageKey("Key1")
                .Email()
                    .WithMessageKey("Key2"))
            .For(model)
            .Validate();

        foreach(var message in result.ErrorMessages)
        {
            Console.WriteLine(message);
        }
    }

Notice that ``MyMessageProvider`` uses ``string`` as a key type, but you can choose any other type you want.

Error codes
------------------
Valit also supports error codes as an alternative approach to messages. You can add one using ``WithErrorCode()`` extension on each validation rule. All error codes are stored inside ``ErrorCodes`` property in the ``IValitResult`` object. The example below present the usage of error codes:

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
            .WithMessageProvider(new MyMessageProvider())
            .Ensure(m => m.Email, _=>_
                .Required()
                    .WithErrorCode(1103)
                .Email()
                    .WithErrorCode(1107))
            .For(model)
            .Validate();

        foreach(var code in result.ErrorCodes)
        {
            Console.WriteLine(code);
        }
    }
