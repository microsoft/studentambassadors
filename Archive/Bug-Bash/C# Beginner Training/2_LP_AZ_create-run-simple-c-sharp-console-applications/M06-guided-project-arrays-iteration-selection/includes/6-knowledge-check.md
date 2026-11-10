---
title: Knowledge check
durationInMinutes: 3
---
## quiz title: Knowledge check

## Multiple Choice

A developer creates an application that uses a `foreach` loop to iterate through the 20 elements contained in an integer array. After completing the application, the developer learns that the array data must be updated to include 40 elements rather than the original 20. The application must examine all of the data in the updated array. Which of the following describes the best approach to ensure that all 40 elements are examined?
( ) Create a second `foreach` loop that iterates through the additional items. {{Incorrect.  This will cause the array elements to be processed twice.}}
(x) No changes are required to the foreach loop. {{Correct! A `foreach` loop will iterate through all of the elements in an array.}}
( ) Place the original `foreach` loop inside an outer `foreach` loop that iterates twice. {{Incorrect. This will cause the array elements to be processed twice.}}

## Multiple Choice

A developer is working on a nested `foreach` structure that will iterate though all of the application's array data. The first array contains the names of locations where water samples were collected. The remaining arrays contain the test results for the samples collected from each named location. Which of the following statements about how the arrays should be processed by the nested `foreach` structure is correct?
( ) Each of the arrays containing samples can be processed by the outer loop, the inner loop will be used to verify the location. {{Incorrect. The outer `foreach` loop can only process one array, so it cannot process each of the arrays containing samples.}}
( ) It doesn't matter which order the arrays are processed since the application has to process all of the data. {{Incorrect. The relationship between outer and inner `foreach` loops is critical. The application will not be able to process all of the array data that's described in this scenario if the nested `foreach` structure is not established correctly.}}
(x) The outer loop must process the array containing locations, the inner loop will process the arrays containing samples. {{Correct! The outer loop will iterate though the locations. The code block of the outer loop will be used to select the samples array for each location, and then process the sample in the inner `foreach` loop.}}
