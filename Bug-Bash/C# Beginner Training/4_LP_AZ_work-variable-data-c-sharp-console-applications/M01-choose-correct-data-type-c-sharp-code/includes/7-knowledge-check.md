---
title: Knowledge check
durationInMinutes: 3
---

## quiz title: Check your knowledge

## Multiple Choice

A piece of code must store whole numeric values between negative and positive `1,000,000`. Which data type should you choose?
( ) float {{That’s incorrect. While `float` would work, its extra precision after the decimal doesn't fit the exact requirement of this scenario.}}
( ) double {{That’s incorrect. While `double` would work, its extra precision after the decimal doesn't fit the exact requirement of this scenario.}}
(x) int {{That’s correct. While `float` or `double` would work, their extra precision after the decimal doesn't fit the exact requirement of this scenario.}}

## Multiple Choice

The code for a game needs to store lots of fractional values representing x, y, and z positions in a large 3D space. It will likely need to perform physics calculations for trajectories and so on. Absolute precision is not required, but it is important that the program runs as efficiently as possible. Which data type is best?
(x) float {{That’s correct. Unlike `int`, float can store fractional numbers, and unlike `decimal`, `float` does not require additional memory to store extra precision that isn't needed in this scenario.}}
( ) decimal {{That’s incorrect. While `decimal` can store large fractional numbers, they require more memory to store all the precision. Furthermore, they're less efficient than float or double. Finally, they can return precise calculated values, but the question says that's not a priority in this situation.}}
( ) int {{That’s incorrect. `int` can't store fractional numbers.}}

## Multiple Choice

Which of the following statements is **true**?
( ) Reference types are stored in the stack. {{That’s incorrect. Reference types are stored in the heap.}}
( ) Value types can only store numbers. {{That’s incorrect. While we focused on integral and floating point data types, `char` is also a value type, and there are other non-numeric value types like struct and enum.}}
(x) Use the `new` operator to create a new instance of a reference type and return its address to the variable. {{That’s correct. Use the `new` operator to create a new instance of a reference type and return its address to the variable.}}