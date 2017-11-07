=====================
Validation rules
=====================

Supported data types
====================
Valit provides validation rules for plenty different data types **with full support for** ``Nullable<T>``. The supported data types are:

- ``Byte``
- ``DateTime``
- ``DateTimeOffset``
- ``Decimal``
- ``Double``
- ``Float``
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

.. note:: ``null`` either on validated property or given value result in rule returning ``false``

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
Examples of tagging rules.