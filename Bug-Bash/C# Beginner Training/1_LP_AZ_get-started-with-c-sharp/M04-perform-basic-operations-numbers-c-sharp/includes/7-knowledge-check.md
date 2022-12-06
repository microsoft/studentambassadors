## quiz title: Check your knowledge

## Multiple Choice

Which of the following lines of code will fail to output the text `Windows 11`?
(x) `Console.WriteLine("Windows " + 7 + 4)` {{Correct!}}
( ) `Console.WriteLine("Windows " + 11)` {{Incorrect. This line correctly concatenates 11 to the string}}
( ) `Console.Write("Windows " + 1 + 1);` {{Incorrect. This line impicitly casts }}
( ) `Console.Write("Windows " + (7 + 4));` {{Incorrect.}}

## Multiple Choice

What is the value of `result`? `int result = 3 + 1 * 5 / 2;`
( ) 10 {{Incorrect. C# follows the same order as PEMDAS.}}
(x) 5 {{Correct.}}
( ) 6 {{Incorrect. C# follows the same order as PEMDAS.}}

## Multiple Choice

What will be the result of the following line of code?  `Console.WriteLine(5 / 10);`
( ) 0.5 {{Incorrect. While 5 / 10 does equal 0.5, since we're using `int` literals C# will represent them differently.}}
(x) 0 {{Correct. Correct!}}
( ) 1 {{Incorrect. Since `5` and `10` are `int` literals, dividing them would normally equal `0.5`, however the `.5` would be truncated.}}

## Multiple Choice

Which of the following lines of code uses the *addition assignment* operator?
(x) `value += 5;` {{Correct. Correct!}}
( ) `value++;` {{Incorrect. This line of code doesn't use the addition assignment operator.}}
( ) value = value + 5; {{Incorrect. This line of code doesn't use the *addition assignment* operator.}}
