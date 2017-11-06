===============
Getting started
===============
This part will guide you through very basic concepts of Valit, including instalation proccess and creating simple validator for domain object.

Adding Valit to your project
----------------------------
Short description

Creating basic validator
-------------------------
In order to create a validator you new to go through few steps. It's worth mentioning that not all of them are mandatory. The steps are: 

- creating new instance of validator using ``Create()`` static method
- choosing validation :doc:`strategy <../strategies/index>` using ``WithStrategy()`` method **(not required)**
- selecting property using ``Ensure()`` method and defining rules for it. 
- Extending rules with :doc:`custom errors <../validation-errors/index>` (such as messages or error codes), :doc:`tags <../validation-rules/index>` and :doc:`conditions <../validation-rules/index>`. **(not required)**
- applying created rules to an object using ``For()`` method

Having the validator created, simply invoke ``Validate()`` method which will produce the result with all the data.

Let's try it out with very practical example. Imagine that you're task is to validate model sent from registration page of your app. The example object might look as follows:

.. sourcecode:: csharp

    public class RegisterModel
    {
        public string Email { get; set; }        
        public string Password { get; set; }
        public ushort Age { get; set ;}
    }

These are the validation criteria:

- ``Email`` is required and needs to be a proper email address
- ``Password`` is required and needs to be at least 10 characters long
- ``Age`` must be greater than 16

This is how Valit handles such scenario:
  
.. sourcecode:: csharp

        void ValidateModel(RegisterModel model)
        {
            var result = ValitRules<RegisterModel>
                .Create()
                .Ensure(m => m.Email, _=>_
                    .Required()
                    .Email())
                .Ensure(m => m.Password, _=>_ 
                    .Required()
                    .MinLength(10))
                .Ensure(m => m.Age, _=>_
                    .IsGreaterThan(16))
                .For(model)
                .Validate();

            if(result.Succeeded)
            {
                // do something on success
            }
            else 
            {
                // do something on failure
            }
        }

Pretty cool, right? Of course, the above example was fairly simple but trust us. From now on, even complicated validation criterias won't scare you anymore ;)

Need help?
-----------------------
If you need some help, feel free to look at more examples on `GitHub <https://github.com/valit-stack/Valit.Examples>`_. Also don't hesitate to open `new issues <https://github.com/valit-stack/Valit/issues>`_ if something could be done better!