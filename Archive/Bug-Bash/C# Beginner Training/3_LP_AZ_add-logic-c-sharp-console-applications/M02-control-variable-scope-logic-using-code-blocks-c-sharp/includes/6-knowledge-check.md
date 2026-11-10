## quiz title: Knowledge check

## Multiple Choice

The `using` statement ...
( ) Affects only the first code block in the code file. {{Incorrect. The `using` statement applies to more than just the first code block in the code file.}}
( ) Affects only the current code block in the code file. {{Incorrect. The `using` statement applies to more than just the current code block in the code file.}}
(x) Affects all of the code in the code file. {{Correct! The `using` statement applies to all of the code in a code file.}}

## Multiple Choice

Which of the following statements is true about showing/removing the curly braces for code blocks associated with an `if` statement?
( ) The curly braces can't be removed from the code block for `else if` and `else` statements. {{Incorrect. You can remove curly braces from the `else if` and `else` statements if the contents of the code block contains a single line of code and if all associated `if`, `else if`, and `else` code blocks only have one line of code and the curly braces removed. All components of that `if-elseif-else` must be consistent in the use of curly braces}}
( ) If the curly braces are removed from the code blocks of an `if-elseif-else`, the white space must also be removed. {{Incorrect. You can keep the `if` statement separate from the next line of code if you want. Always choose the option that is more readable.}}
(x) Always choose a style that improves readability. {{Correct! Code readability should always be a consideration when deciding whether to remove the curly braces from the code blocks associated with an `if` statement.}}

## Multiple Choice

A developer writes some code that includes an if statement code block. They initialize one integer variable above (outside) of the code block and a second integer variable on the first line inside of the code block. On the next line inside the code block they added the value of the second variable to the value of the first variable. They write code to display the value of the first integer below the code block. What is the result when the code that is used to display the first integer is executed?
(x) No error is generated and the integer value is displayed. The value is the sum of the first and second integer. {{Correct! Since the first integer is initialized above the if statement code it is still in-scope after the code block. Also, since both integers are in-scope and initialized with values inside the code block, the addition of the values executes correctly. Finally, even though the second integer does not exist outside of the code block, the first integer retains any changes to its value that occurred inside the code block.}}
( ) No error is generated and the integer value is displayed. The value is the initialized value from above the code block. {{Incorrect. The value is displayed as the sum of the two integers.}}
( ) An error is generated because the first variable is not in-scope after the code block. {{Incorrect. No error is generated. The first variable was initialized above the code block and is still in-scope both inside and after the code block.}}
