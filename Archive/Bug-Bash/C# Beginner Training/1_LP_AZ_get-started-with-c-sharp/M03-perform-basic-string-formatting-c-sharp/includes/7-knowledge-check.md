## quiz title: Knowledge check

## Multiple Choice

Which of the following escape sequences would you use to add double-quotes to your literal string?
( ) \q {{Incorrect. \q isn't a valid escape sequence.}}
( ) \'{{Incorrect. \' is the escape sequence for a single quote, not a double-quote.}}
(x) \" {{Correct. Correct!}}

## Multiple Choice

Which of the following lines of code correctly uses string interpolation assuming that the variable `value` is a string?
( ) '`Console.WriteLine(@"My value: {value}");`' {{Incorrect. This line uses the at `@` symbol instead of the dollar `$` symbol as the prefix for string interpolation.}}
(x) '`Console.WriteLine($"My value: {value}");`' {{Correct!}}
( ) '`Console.WriteLine(@"My value: [value]");`' {{Incorrect. This line uses the at `@` symbol instead of the dollar `$` symbol, and square brackets instead of curly braces for the interpolation expression.}}

## Multiple Choice

You embedded Unicode characters in your strings to present a special message in Thai, however the message is only displayed as question mark characters.  What happened?
( ) You're missing the \u escape sequence for Unicode characters.{{Incorrect. If you don't use the \u escape sequence for Unicode characters, you won't see question marks.  You'll see the numbers.}}
( ) You used the wrong Unicode characters. {{Incorrect. This is unlikely.  It would only be true if all the Unicode characters were the same value representing a question mark -- \u003F.}}
(x) The user's console doesn't support Unicode characters. {{Correct.Correct!}}

## Multiple Choice

Which of the following lines of code will append a single `\` to the string `directory`?
( ) '`directory = directory + "\";`' {{Incorrect. This line escapes the `"` character and results in an error.}}
( ) '`directory = directory + '\';`' {{Incorrect. This line escapes the `'` character and results in an error.}}
(x) '`directory = directory + @"\";`' {{Correct. The `@` symbol creates a verbatim string where it is unnecssary to escape the `\`.}}