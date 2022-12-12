---
title: Knowledge check
durationInMinutes: 3
---

## quiz title: Check your knowledge

## Multiple Choice

Which of the following options will output data in a tab-delimited format (in other words, using a tab between each data element)?
( ) Use `PadRight()` equal to four blank spaces {{That's incorrect. Padding doesn't automatically create blank spaces if the value's length meets or exceeds the padding.}}
( ) Use `PadLeft()` equal to four blank spaces {{That's incorrect. Padding doesn't automatically create blank spaces if the value's length meets or exceeds the padding.}}
(x) Use `\\t` between the values {{That's correct. Padding doesn't automatically create blank spaces if the value's length meets or exceeds the padding.}}

## Multiple Choice

Which format specifier will present a decimal value with the following format to an en-US audience: `12,345.67`
( ) `0:C` {{That's incorrect. Though it looks similar, the numeric value is not necessarily currency.}}
( ) `0:H` {{That's incorrect. `H` isn't a known format specifier.}}
(x) `0:N2` {{That's correct. `N2` is the correct format specifier!}}

## Multiple Choice

Which character must be used as a directive to perform string interpolation?
(x) `$` {{That's correct. `@` is used to create a verbatim string literal, not perform string interpolation, and `%` isn't a valid directive.}}
( ) `@` {{That's incorrect. `@` is used to create a verbatim string literal, not perform string interpolation.}}
( ) `%` {{That's incorrect. `%` isn't a valid directive.}}
