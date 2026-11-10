## quiz title: Check your knowledge

## Multiple Choice

Which of the following variable names should or must be **avoided**?
(x) $DATA {{Correct. The `$` can't be used in a variable name. Furthermore, you shouldn't use all upper case characters for a variable name.}}
( ) registrationComplete {{Incorrect. `registrationComplete` is a valid variable name.}}
( ) flag {{Incorrect. `flag` is a valid variable name.}}

## Multiple Choice

What is the problem with this line of code: `var message;`
( ) `var` isn't a data type. {{Incorrect. It's true that `var` isn't a data type, but that's not the problem with this code.}}
(x) Use of `var` keyword without initializing the variable {{Correct!}}
( ) A variable named `message` should always be a string. {{Incorrect. This isn't necessarily true. It depends on the context.}}

## Multiple Choice

Which of the following is the output of `Console.WriteLine(34.40M)`?
( ) `34.40M` {{Incorrect. An `M` is a literal suffix.}}
( ) `34.4` {{Incorrect. Using the decimal literal `M` or `m` will print a number that includes values after the decimal point.}}
(x) `34.40` {{Correct!}}

## Multiple Choice

Which of the following lines of code creates a variable correctly?
( ) `int x = 12.3m;` {{Incorrect. An `int` can't be set to a literal decimal value.}}
(x) `decimal x = 12.3m;` {{Correct!}}
( ) `bool x = 'False';` {{Incorrect. The first problem is that you can't use a single-quote to create a `string` literal. The second problem is that you can't set a `bool` to a `string` or `char` literal.}}
