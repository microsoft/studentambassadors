---
title: Knowledge check
durationInMinutes: 3
---
## quiz title: Knowledge check

## Multiple Choice

A developer is working on a nested `foreach` structure that will iterate though the application's array data. The first array contains the names of 10 geographic regions. The remaining arrays are based on the 10 regions, and contain the population of every city in that region that has a population greater than 1 million. The values in the population arrays are ordered from largest to smallest. The application must report average population for the 25 most populated cities in each region. What can the developer do to ensure that the application knows when it has reached the 25th largest population?
() The developer needs to insert a "marker value", such as a `0`, into each of the population arrays at index number 25, and then stop adding values to the sum once the marker value is detected. {{Incorrect. The developer should not modify application data. There are ways to track the number of array elements that have been processed within a `foreach` loop.}}
() The developer needs to check the index number of the current array element in the code block of the inner `foreach` loop and ensure it is less than 25 before adding the value to the sum. {{Incorrect. A `foreach` loop does not have a mechanism for checking the index number of array elements.}}
(x) The developer needs to increment a counter in the code block of the inner `foreach` loop that counts the population values that have been added to the sum and ensure that only the first 25 values are summed. {{Correct! The developer should use a counter that increments inside the `foreach` loop.}}

## Multiple Choice

A developer is with two other developers to update a collection of applications. The developers will use code comments during the update process. Which of the following describes an appropriate use of code comments?
( ) The developers use line and block comments to identify each individual change so that the other developers know where changes have been made. {{Incorrect. Code comments should not be used to describe individual code lines. In this case it would be better to summarize changes in a single block comment at the top of the files that contain updates.}}
( ) To ensure that historical information and context are not lost, the developers leave all existing code comments intact. New comments are added to indicate when old comments no longer apply. {{Incorrect. Old comments that no longer apply to the current application can be confusing and should not be retained. A history of the application should be documented in a change log.}}
(x)  The developers should summarize changes using block comments. {{Correct! Using a block comment to summarize the changes implemented during an update is a good use of code comments. A single block comment at the top of the files that contain updates is often sufficient.}}
