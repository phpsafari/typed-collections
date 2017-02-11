[![Build Status](https://travis-ci.org/vistik/type-hinted-arrays.svg?branch=master)](https://travis-ci.org/vistik/type-hinted-arrays) [![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/vistik/type-hinted-arrays/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/vistik/type-hinted-arrays/?branch=master) [![Coverage Status](https://coveralls.io/repos/vistik/type-hinted-arrays/badge.svg?branch=master)](https://coveralls.io/r/vistik/type-hinted-arrays?branch=master) [![Dependency Status](https://www.versioneye.com/user/projects/54e7ae0ed1ec5734f4000e02/badge.svg?style=flat)](https://www.versioneye.com/user/projects/54e7ae0ed1ec5734f4000e02)

### What is this?

This is a very simple way to make arrays type hinted!

`$list = new UserCollection(new User());`

OK

`$list = new UserCollection('User');`

Will throw:

`Vistik\Exception\InvalidTypeException: Item (string) 'User' is not a Vistik\Example\User object!`

### Install
Run `composer require vistik/type-hinted-arrays`

### Use build in Collections for primitives
Out-of-the-box collections for:
 - Booleans
 - Integers
 - Floats
 - Strings
 - Emails
 - Numbers (float or int)

### Do I have to create a type for each list? Yes, but
Look how easy it is:

    class UserCollection extends TypedCollection{
        protected $type = 'Vistik\Example\User';
    }

2 simple steps

1) Create a Class eg. `AccountCollection` extend `TypedCollection`  
2) Just replace `protected $type = 'Vistik\Example\User';` with your class

or

If the check is more then just a `is_a` check, you can overwrite the function: `isValidItem($item)` in your new Collection class

### Features

* Build upon [Illuminate\Support\Collection](https://github.com/illuminate/support)
* Very simple to implement custom Collections
