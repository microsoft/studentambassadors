## quiz title: Knowledge check

## Multiple Choice

What does the following code accomplish? `var value = (int) dividend / (int) divisor;`
(x) Casts the operands to truncate the result {{Correct. The operands are casted to the int data type which will create an implicitly typed int result}}
( ) Declares an explicitly typed int variable {{Incorrect. The var keyword creates an implicitly typed variable}}
( ) Casts the operands to prevent truncating the result {{Incorrect. The operands are casted to the int data type which will truncate the result}}

## Multiple Choice

Why does the tab appear to be a space in the output of the following code? `Console.WriteLine("Student\tGrade");`
( ) The tab escape sequence is incorrect {{Incorrect. `\t` is the correct escape sequence for tab}}
(x) The next tab stop after `Student` is simply one space wide {{Correct. Printing a tab fills variable length whitespace until a position divisible by 4 is reached}}
( ) The tab escape sequence needs to be doubled (`\t\t`) to work {{Incorrect. A single `t` will display a tab correctly}}

## Multiple Choice

What is wrong with the following code? `int sophiaSum; Console.WriteLine("Sophia: " + sophiaSum);`
(x) `sophiaSum` is not initialized before use {{Correct. You must set a variable to a value before you can reference the value from the variable }}
( ) `sophiaSum` is not implicitly typed to a string {{Incorrect. Using Console.WriteLine will implicitly convert convert variables into strings}}
( ) `sophiaSum` should use the var keyword {{Incorrect. var variables need to be initialized immediately}}
