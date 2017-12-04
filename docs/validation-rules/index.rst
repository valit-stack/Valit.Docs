=====================
Validation rules
=====================

Supported data types
====================
Valit provides validation rules for plenty different data types **with full support for** ``Nullable<T>``. The supported data types are:

- ``Boolean``
- ``Byte``
- ``DateTime``
- ``DateTimeOffset``
- ``Decimal``
- ``Double``
- ``Float``
- ``Guid``
- ``IEnumerable<T>``
- ``Int16``
- ``Int32``
- ``Int64``
- ``SByte``
- ``String``
- ``TimeSpan``
- ``UInt16``
- ``UInt32``
- ``UInt64``

Available validation rules
==========================
Because of differences between particular data types, each one contains its own set of available validation rules. However, there are two general extensions which can be applied on any type you want:

- ``Satisifies<T>(Predicate<T>)`` - checks whether given predicate returns ``true``.
- ``Required<T>()`` - checks whether given **reference type** is not ``null``. 

Below you can find the full list of available validation rules for supported data types.

.. note:: ``null`` either on validated property or given value always results rule returning ``false``

Boolean
-------
- ``IsTrue(bool|bool?)`` - checks whether ``bool|bool?`` property is equal to ``true``.
- ``IsFalse(bool|bool?)`` - checks whether ``bool|bool?`` property is equal to ``false``.
- ``IsEqualTo(bool|bool?)`` - checks whether ``bool|bool?`` property is equal to given value.
- ``Required()`` - checks whether ``bool?`` property is not ``null``.

Byte  
----
- ``IsEqualTo(byte|byte?)`` - checks whether ``byte|byte?`` property is equal to given value.
- ``IsGreaterThan(byte|byte?)`` - checks whether ``byte|byte?`` property is greater than given value.
- ``IsGreaterThanOrEqualTo(byte|byte?)`` - checks whether ``byte|byte?`` property is greater than or equal to given value.  
- ``IsLessThan(byte|byte?)`` - checks whether ``byte|byte?`` property is less than given value.
- ``IsLessThanOrEqualTo(byte|byte?)`` - checks whether ``byte|byte?`` property is less than or equal to given value.
- ``IsNonZero()`` - checks whether ``byte|byte?`` property is not a zero.
- ``Required()`` - checks whether ``byte?`` property is not ``null``.

DateTime
--------
- ``IsAfter(DateTime|DateTime?)`` - checks whether ``DateTime|DateTime?`` property is after (greater than) given value.
- ``IsAfterOrSameAs(DateTime|DateTime?)`` - checks whether ``DateTime|DateTime?`` property is after or same as (greater than or equal to) given value.
- ``IsAfterNow()`` - checks whether ``DateTime|DateTime?`` property is after (greater than) ``DateTime.Now``.
- ``IsAfterUtcNow()`` - checks whether ``DateTime|DateTime?`` property is after (greater than) ``DateTime.UtcNow``.
- ``IsBefore(DateTime|DateTime?)`` - checks whether ``DateTime|DateTime?`` property is before (less than) given value.
- ``IsBeforeOrSameAs(DateTime|DateTime?)`` - checks whether ``DateTime|DateTime?`` property is before or same as (less than or equal to) given value.
- ``IsBeforeNow()`` - checks whether ``DateTime|DateTime?`` property is before (less than) ``DateTime.Now``.
- ``IsBeforeUtcNow()`` - checks whether ``DateTime|DateTime?`` property is before (less than) ``DateTime.UtcNow``.
- ``IsSameAs(DateTime|DateTime?)`` - checks whether ``DateTime|DateTime?`` property is same as (equal to) given value.
- ``Required()`` - checks whether ``DateTime?`` property is not ``null``.

DateTimeOffset
--------------
- ``IsAfter(DateTimeOffset|DateTimeOffset?)`` - checks whether ``DateTimeOffset|DateTimeOffset?`` property is after (greater than) given value.
- ``IsAfterOrSameAs(DateTimeOffset|DateTimeOffset?)`` - checks whether ``DateTimeOffset|DateTimeOffset?`` property is after or same as (greater than or equal to) given value.
- ``IsAfterNow()`` - checks whether ``DateTimeOffset|DateTimeOffset?`` property is after (greater than) ``DateTime.Now``.
- ``IsAfterUtcNow()`` - checks whether ``DateTimeOffset|DateTimeOffset?`` property is after (greater than) ``DateTime.UtcNow``.
- ``IsBefore(DateTimeOffset|DateTimeOffset?)`` - checks whether ``DateTimeOffset|DateTimeOffset?`` property is before (less than) given value.
- ``IsBeforeOrSameAs(DateTimeOffset|DateTimeOffset?)`` - checks whether ``DateTimeOffset|DateTimeOffset?`` property is before or same as (less than or equal to) given value.
- ``IsBeforeNow()`` - checks whether ``DateTimeOffset|DateTimeOffset?`` property is before (less than) ``DateTime.Now``.
- ``IsBeforeUtcNow()`` - checks whether ``DateTimeOffset|DateTimeOffset?`` property is before (less than) ``DateTime.UtcNow``.
- ``IsSameAs(DateTimeOffset|DateTimeOffset?)`` - checks whether ``DateTimeOffset|DateTimeOffset?`` property is same as (equal to) given value.
- ``Required()`` - checks whether ``DateTimeOffset?`` property is not ``null``.

Decimal  
-------
- ``IsEqualTo(decimal|decimal?)`` - checks whether ``decimal|decimal?`` property is equal to given value.
- ``IsGreaterThan(decimal|decimal?)`` - checks whether ``decimal|decimal?`` property is greater than given value.
- ``IsGreaterThanOrEqualTo(decimal|decimal?)`` - checks whether ``decimal|decimal?`` property is greater than or equal to given value.  
- ``IsLessThan(decimal|decimal?)`` - checks whether ``decimal|decimal?`` property is less than given value.
- ``IsLessThanOrEqualTo(decimal|decimal?)`` - checks whether ``decimal|decimal?`` property is less than or equal to given value.
- ``IsNonZero()`` - checks whether ``decimal|decimal?`` property is not a zero.
- ``IsNegative()`` - checks whether ``decimal|decimal?`` property is negative **(less than zero)**.
- ``IsPositive()`` - checks whether ``decimal|decimal?`` property is positive **(greater than zero)**.
- ``Required()`` - checks whether ``decimal?`` property is not ``null``.

Double  
-------
- ``IsEqualTo(double|double?)`` - checks whether ``double|double?`` property is equal to given value.
- ``IsGreaterThan(double|double?)`` - checks whether ``double|double?`` property is greater than given value.
- ``IsGreaterThanOrEqualTo(double|double?)`` - checks whether ``double|double?`` property is greater than or equal to given value.  
- ``IsLessThan(double|double?)`` - checks whether ``double|double?`` property is less than given value.
- ``IsLessThanOrEqualTo(double|double?)`` - checks whether ``double|double?`` property is less than or equal to given value.
- ``IsNonZero()`` - checks whether ``double|double?`` property is not a zero.
- ``IsNegative()`` - checks whether ``double|double?`` property is negative **(less than zero)**.
- ``IsPositive()`` - checks whether ``double|double?`` property is positive **(greater than zero)**.
- ``IsNaN()`` - checks whether ``double|double?`` property is ``double.NaN``.
- ``IsNumber()`` - checks whether ``double|double?`` property is not ``double.NaN``.
- ``Required()`` - checks whether ``double?`` property is not ``null``.

Float  
-------
- ``IsEqualTo(float|float?)`` - checks whether ``float|float?`` property is equal to given value.
- ``IsGreaterThan(float|float?)`` - checks whether ``float|float?`` property is greater than given value.
- ``IsGreaterThanOrEqualTo(float|float?)`` - checks whether ``float|float?`` property is greater than or equal to given value.  
- ``IsLessThan(float|float?)`` - checks whether ``float|float?`` property is less than given value.
- ``IsLessThanOrEqualTo(float|float?)`` - checks whether ``float|float?`` property is less than or equal to given value.
- ``IsNonZero()`` - checks whether ``float|float?`` property is not a zero.
- ``IsNegative()`` - checks whether ``float|float?`` property is negative **(less than zero)**.
- ``IsPositive()`` - checks whether ``float|float?`` property is positive **(greater than zero)**.
- ``IsNaN()`` - checks whether ``float|float?`` property is ``float.NaN``.
- ``IsNumber()`` - checks whether ``float|float?`` property is not ``float.NaN``.
- ``Required()`` - checks whether ``float?`` property is not ``null``.

Guid  
----
- ``IsEqualTo(Guid|Guid?)`` - checks whether ``Guid|Guid?`` property is equal to given value.
- ``IsNotEmpty()`` - checks whether ``Guid|Guid?`` property is not ``Guid.Empty``.
- ``Required()`` - checks whether ``Guid?`` property is not ``null``.

IEnumerable<T>
--------------
- ``MinItems(int)`` - checks whether collection contains at least given number of elements.
- ``MaxItems(int)`` - checks whether collection contains at most given number of elements.

Int16  
-------
- ``IsEqualTo(short|short?)`` - checks whether ``short|short?`` property is equal to given value.
- ``IsGreaterThan(short|short?)`` - checks whether ``short|short?`` property is greater than given value.
- ``IsGreaterThanOrEqualTo(short|short?)`` - checks whether ``short|short?`` property is greater than or equal to given value.  
- ``IsLessThan(short|short?)`` - checks whether ``short|short?`` property is less than given value.
- ``IsLessThanOrEqualTo(short|short?)`` - checks whether ``short|short?`` property is less than or equal to given value.
- ``IsNonZero()`` - checks whether ``short|short?`` property is not a zero.
- ``IsNegative()`` - checks whether ``short|short?`` property is negative **(less than zero)**.
- ``IsPositive()`` - checks whether ``short|short?`` property is positive **(greater than zero)**.
- ``Required()`` - checks whether ``short?`` property is not ``null``.

Int32  
-------
- ``IsEqualTo(int|int?)`` - checks whether ``int|int?`` property is equal to given value.
- ``IsGreaterThan(int|int?)`` - checks whether ``int|int?`` property is greater than given value.
- ``IsGreaterThanOrEqualTo(int|int?)`` - checks whether ``int|int?`` property is greater than or equal to given value.  
- ``IsLessThan(int|int?)`` - checks whether ``int|int?`` property is less than given value.
- ``IsLessThanOrEqualTo(int|int?)`` - checks whether ``int|int?`` property is less than or equal to given value.
- ``IsNonZero()`` - checks whether ``int|int?`` property is not a zero.
- ``IsNegative()`` - checks whether ``int|int?`` property is negative **(less than zero)**.
- ``IsPositive()`` - checks whether ``int|int?`` property is positive **(greater than zero)**.
- ``Required()`` - checks whether ``int?`` property is not ``null``.

Int64  
-------
- ``IsEqualTo(long|long?)`` - checks whether ``long|long?`` property is equal to given value.
- ``IsGreaterThan(long|long?)`` - checks whether ``long|long?`` property is greater than given value.
- ``IsGreaterThanOrEqualTo(long|long?)`` - checks whether ``long|long?`` property is greater than or equal to given value.  
- ``IsLessThan(long|long?)`` - checks whether ``long|long?`` property is less than given value.
- ``IsLessThanOrEqualTo(long|long?)`` - checks whether ``long|long?`` property is less than or equal to given value.
- ``IsNonZero()`` - checks whether ``long|long?`` property is not a zero.
- ``IsNegative()`` - checks whether ``long|long?`` property is negative **(less than zero)**.
- ``IsPositive()`` - checks whether ``long|long?`` property is positive **(greater than zero)**.
- ``Required()`` - checks whether ``long?`` property is not ``null``.

SByte  
-------
- ``IsEqualTo(sbyte|sbyte?)`` - checks whether ``sbyte|sbyte?`` property is equal to given value.
- ``IsGreaterThan(sbyte|sbyte?)`` - checks whether ``sbyte|sbyte?`` property is greater than given value.
- ``IsGreaterThanOrEqualTo(sbyte|sbyte?)`` - checks whether ``sbyte|sbyte?`` property is greater than or equal to given value.  
- ``IsLessThan(sbyte|sbyte?)`` - checks whether ``sbyte|sbyte?`` property is less than given value.
- ``IsLessThanOrEqualTo(sbyte|sbyte?)`` - checks whether ``sbyte|sbyte?`` property is less than or equal to given value.
- ``IsNonZero()`` - checks whether ``sbyte|sbyte?`` property is not a zero.
- ``IsNegative()`` - checks whether ``sbyte|sbyte?`` property is negative **(less than zero)**.
- ``IsPositive()`` - checks whether ``sbyte|sbyte?`` property is positive **(greater than zero)**.
- ``Required()`` - checks whether ``sbyte?`` property is not ``null``.

String  
-------
- ``Email()`` - checks whether ``string`` property is a correct email address.
- ``IsEqualTo(string)`` - checks whether ``string`` property is equal to given value.
- ``Matches(string)`` - checks whether ``string`` property matches given **regex**.
- ``MinLength(int)`` - checks whether ``string`` property has at least given number of characters.
- ``MaxLength(int)`` - checks whether ``string`` property has at most given number of characters.
- ``Required()`` - checks whether ``string`` property is not ``null`` or empty.

TimeSpan  
--------
- ``IsEqualTo(TimeSpan|TimeSpan?)`` - checks whether ``TimeSpan|TimeSpan?`` property is equal to given value.
- ``IsGreaterThan(TimeSpan|TimeSpan?)`` - checks whether ``TimeSpan|TimeSpan?`` property is greater than given value.
- ``IsGreaterThanOrEqualTo(TimeSpan|TimeSpan?)`` - checks whether ``TimeSpan|TimeSpan?`` property is greater than or equal to given value.  
- ``IsLessThan(TimeSpan|TimeSpan?)`` - checks whether ``TimeSpan|TimeSpan?`` property is less than given value.
- ``IsLessThanOrEqualTo(TimeSpan|TimeSpan?)`` - checks whether ``TimeSpan|TimeSpan?`` property is less than or equal to given value.
- ``IsNonZero()`` - checks whether ``TimeSpan|TimeSpan?`` property is not a zero.
- ``Required()`` - checks whether ``TimeSpan?`` property is not ``null``.

UInt16  
-------
- ``IsEqualTo(ushort|ushort?)`` - checks whether ``ushort|ushort?`` property is equal to given value.
- ``IsGreaterThan(ushort|ushort?)`` - checks whether ``ushort|ushort?`` property is greater than given value.
- ``IsGreaterThanOrEqualTo(ushort|ushort?)`` - checks whether ``ushort|ushort?`` property is greater than or equal to given value.  
- ``IsLessThan(ushort|ushort?)`` - checks whether ``ushort|ushort?`` property is less than given value.
- ``IsLessThanOrEqualTo(ushort|ushort?)`` - checks whether ``ushort|ushort?`` property is less than or equal to given value.
- ``IsNonZero()`` - checks whether ``ushort|ushort?`` property is not a zero.
- ``IsNegative()`` - checks whether ``ushort|ushort?`` property is negative **(less than zero)**.
- ``IsPositive()`` - checks whether ``ushort|ushort?`` property is positive **(greater than zero)**.
- ``Required()`` - checks whether ``ushort?`` property is not ``null``.

UInt32  
-------
- ``IsEqualTo(uint|uint?)`` - checks whether ``uint|uint?`` property is equal to given value.
- ``IsGreaterThan(uint|uint?)`` - checks whether ``uint|uint?`` property is greater than given value.
- ``IsGreaterThanOrEqualTo(uint|uint?)`` - checks whether ``uint|uint?`` property is greater than or equal to given value.  
- ``IsLessThan(uint|uint?)`` - checks whether ``uint|uint?`` property is less than given value.
- ``IsLessThanOrEqualTo(uint|uint?)`` - checks whether ``uint|uint?`` property is less than or equal to given value.
- ``IsNonZero()`` - checks whether ``uint|uint?`` property is not a zero.
- ``IsNegative()`` - checks whether ``uint|uint?`` property is negative **(less than zero)**.
- ``IsPositive()`` - checks whether ``uint|uint?`` property is positive **(greater than zero)**.
- ``Required()`` - checks whether ``uint?`` property is not ``null``.

UInt64  
-------
- ``IsEqualTo(ulong|ulong?)`` - checks whether ``ulong|ulong?`` property is equal to given value.
- ``IsGreaterThan(ulong|ulong?)`` - checks whether ``ulong|ulong?`` property is greater than given value.
- ``IsGreaterThanOrEqualTo(ulong|ulong?)`` - checks whether ``ulong|ulong?`` property is greater than or equal to given value.  
- ``IsLessThan(ulong|ulong?)`` - checks whether ``ulong|ulong?`` property is less than given value.
- ``IsLessThanOrEqualTo(ulong|ulong?)`` - checks whether ``ulong|ulong?`` property is less than or equal to given value.
- ``IsNonZero()`` - checks whether ``ulong|ulong?`` property is not a zero.
- ``IsNegative()`` - checks whether ``ulong|ulong?`` property is negative **(less than zero)**.
- ``IsPositive()`` - checks whether ``ulong|ulong?`` property is positive **(greater than zero)**.
- ``Required()`` - checks whether ``ulong?`` property is not ``null``.

Validating nested objects
=========================
Sometimes there could be need to validate nested objects. You can do this by creating your own ``RulesProvider``. Let's say we have the following model:

.. sourcecode:: csharp

    public class OrderModel
    {
        public AddressModel Address { get; set; }
    }

    public class AddressModel
    {
        public string City { get; set; }
        public string Street { get; set; }
    }

We'd like to be sure that ``City`` and ``Street`` in our ``OrderModel`` are not empty. To do that we have to create the following provider:

.. sourcecode:: csharp

    class AddressModelRulesProvider : IValitRulesProvider<AddressModel>
    {
        public IEnumerable<IValitRule<AddressModel>> GetRules()
            => ValitRules<AddressModel>
            	.Create()
            	.Ensure(m => m.City, _=>_
            		.Required())
            	.Ensure(m => m.Street, _=>_
            		.Required())
            	.GetAllRules();
    }

Then we can validate our ``OrderModel`` using the created provider:

.. sourcecode:: csharp

    void ValidateModel(OrderModel model)
    {
    	var result = ValitRules<OrderModel>
    		.Create()
        	.Ensure(m => m.Address, new AddressModelRulesProvider())
        	.For(model)
        	.Validate();
    }

Using ```IValitRulesProvider<TObject>``` has many adventages:

- You can reduce number of lines inside ```IValitRules<TObject>``` instance
- You don't have to duplicate the code for each new, complex type. You can use already existing one.
- You have single place in your code when it comes to changes
- You can easily register your provider in IoC container and provide it across your app     

```IValitRulesProvider<TObject>``` can be also easily transformed into :doc:`valitator <../valitators/index>`.

Validating collections
======================

Using Valit you can also easily validate collections. Let's assume that you have following model:

.. sourcecode:: csharp

    public class ContactModel
    {
        public IEnumerable<string> Emails { get; set; }
    }

We'd like to check whether each item in ``Emails`` list is not ``null`` or ``string.Empty`` and is also valid email address. To validate collections use ``EnsureFor``:

.. sourcecode:: csharp

    void Validate(ContactModel model)
    {
    	var result = ValitRules<ContactModel>
    		.Create()
            .WithStrategy(picker => picker.FailFast)
            .EnsureFor(m => m.Emails, _=>_
            	.Required()
                .WithMessage("Email list is empty")
                .Email()
                .WithMessage("Email list contains incorrect addresses"))
            .For(model)
            .Validate();
    }

Conditional rules
=================
In some cases there might be need to apply certain validation rules only if specific conditions are fulfilled. Valit allows you to do this using ``When()`` extension which can be applied on each rule. Let's say we have the following model:

.. sourcecode:: csharp

    public class RegisterModel
    {
        public string Email { get; set; }        
        public string Password { get; set; }
        public string CompanyName { get; set; }
        public bool IsCompanyMember { get; set; }
    }

We'd like ``CompanyName`` to be required only if the user belongs to some company (defined by ``IsCompanyMemeber``). Of course, we could create two separate validators to handle both scenarios, but a lot of code would be duplicated. That's where conditional rules come into play:

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
                .Ensure(m => m.CompanyName, _=>_
                    .Required()
                        .When(m => m.IsCompanyMember))
                .For(model)
                .Validate();
        }
    

Using ``When()`` we created simple validation condition which solves the issue. 

.. note:: You can apply as much conditions as you want on each rule. If so, they will be merged into one condition using **logical AND** operator.

Tagging rules
=============
Each validation rule can have its own set of tags. Tags are used for defining subset of rules that will be checked during the validation process. To add tags to the validation rule use ``Tag()`` extension. The code below presents the example usage:

.. sourcecode:: csharp

    public class RegisterModel
    {
        public string Email { get; set; }        
        public int Age { get; set; }
    }

    void ValidateModel(RegisterModel model)
    {
        IValitRules<RegisterModel> valitRules = ValitRules<RegisterModel>
            .Create()
            .Ensure(m => m.Email, _=>_
                .Required()
                    .Tag("A")
                .Email()
                    .Tag("A", "B"))
            .Ensure(m => m.Age, _=>_
                .IsGreaterThan(16)
                    .Tag("B"))
            .For(model);

        IValitResult result1 = valitRules.Validate("A"); // Checks Required, Email
        IValitResult result2 = valitRules.Validate("B"); //Checks Email, IsGreaterThan
        IValitResult result3 = valitRules.Validate("A", "B"); //Checks all rules 
    }

As you see in the example above, instead of invoking the ``Validate()`` right after the ``For()`` method, we assigned the rules to the variable. Then, using the ``Validate()`` overload which accepts tags, we created three different validation processes. That gave as a lot of flexibility by creating one general set of validation rules instead of three separated. It is important that set of tags passed to the ``Validate()`` method defines that **each rule must have at least one of them, NOT all.** 

``Validate()`` method has also an overload which accepts ``Predicate<IValitRule<TModel>>``:

.. sourcecode:: csharp

    var result1 = rules.Validate(rule => rule.Tags.Any(tag => tag == "A")); // Checks Required, Email


``ValitRules<T>`` object also provides three methods for getting set of your validation rules. The methods are:

- ``GetAllRules()`` - gets all rules.
- ``GetTaggedRules()`` - gets rules which has at least one tag.
- ``GetUntaggedRules()`` - gets rules with no tags.

Of course if you want to get rules with the specific tags, you can use **Linq** for that purpose like in the example below:

.. sourcecode:: csharp

        IEnumerable<IValitRule<RegisterModel>> rulesOnlyWithATag= ValitRules<RegisterModel>
            .Create()
            .Ensure(m => m.Email, _=>_
                .Required().Tag("A")
                .Email().Tag("B"))
            .GetTaggedRules()
                .Where(rule => rule.Tags.Contains("A")); // only Required method is selected

Having the set of rules, you can use them for instantiating new ``ValitRules<T>`` object using ``Create()`` method overload:

.. sourcecode:: csharp

    void ValidateModel(RegisterModel model, IEnumerable<IValitRule<RegisterModel>> rulesOnlyWithATag)
    {
        IValitResult result = ValitRules<RegisterModel>
            .Create(rulesOnlyWithATag)
            .For(model)
            .Validate(); // validates the model using only Required rule on Email property
    }
