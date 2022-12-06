## quiz title: Knowledge check

## Multiple Choice

When is it appropriate to use a `switch-case` construct rather than a `if-elseif-else` construct?
(x) when the number of `else if` code blocks required is greater than 2-3 {{Correct! When the number of `else if` code blocks becomes larger than 2-3, the code can become difficult to read, and the `switch-case` construct is preferable}}
( ) when the number of `case` patterns is small {{Incorrect. If there are fewer than 2-3 `case` patterns in the selection list of a `switch` statement, an `if-elseif-else` construct may be the better choice.}}
( ) when the selection statement is inside of a loop {{Incorrect. Whether the selection statement is inside of a loop or not makes not difference when choosing between a `switch-case` construct and a `if-elseif-else` construct.}}

## Multiple Choice

Why do we choose a `for` statement rather than a `foreach` statement when processing the contents of a multidimensional array?
( ) `for` statements do a better job of examining each array item separately {{Incorrect. A `foreach` statement will process each array item separately.}}
( ) `foreach` statements do a better job of examining each array item separately {{Incorrect. Although a `foreach` statement will process each array item separately, that is more about when to choose a `foreach` rather than when to choose a `for` statement.}}
(x) `for` statements enable us to treat array dimensions separately {{Correct! When processing the contents of a multidimensional array, we often want to loop through the array dimensions separately. The `for` statement provides better support for doing this.}}

## Multiple Choice

Which of the following describes a reason why is it important to scope a variable at its lowest necessary level?
( ) it ensures that when a variable is declared outside of a code block, the variable can be accessed inside the code block before it has been assigned a value {{Incorrect. A variable that is declared outside of a code block, must be assigned a value inside the code block before it can be accessed. If not, a build error will occur.}}
(x) it ensures that our app resources and security footprint are kept small {{Correct. Keeping variables scoped at the lowest necessary level enables better resource management and helps to minimize the attack profile of the application.}}
( ) it ensures that the variable can be accessed within the lowest level code branches within our application {{Incorrect. Scoping a variable at its lowest necessary level will not ensure the variable is accessible from all low level code branches within an application.}}
