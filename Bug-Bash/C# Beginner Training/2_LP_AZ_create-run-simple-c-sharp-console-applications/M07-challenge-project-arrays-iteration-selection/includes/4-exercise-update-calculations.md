---
title: Exercise - Update your calculated values
durationInMinutes: 3
---
The Student Grading application is used to calculate and report student grades based on their graded exam and extra credit assignments. Your goal in this challenge is to update the code that calculates student grades in accordance with the teacher's updated requirements.

## Specification

In this second challenge exercise, you need to instantiate the variables that are required for the updated score report, complete the required calculations, and then update the `Console.WriteLine()` statement that writes student grades to the console.

Your updated application must:

- use the existing arrays and array values for all student grade calculations
- use the nested structure provided by the existing `foreach` and `if` statements
- calculate the sum of exam and extra credit assignment scores using variables from the first exercise or the original code
- calculate the average for exam scores and extra credit scores using variables from the first exercise or the original code
- calculate the final numeric score as follows: add 10% of the extra credit score sum to the exam score sum, and then divide that value by the number of exams
- calculate the extra credit points earned as follows: divide 10% of the extra credit score sum by the number of exams

> [!TIP]
> You will need to use `(decimal)` casting in your equations to preserve the fractional component during your calculations

The required score report format is:

```Output
Student         Exam Score      Overall Grade   Extra Credit

Sophia          92.2            95.88   A       92 (3.68 pts)
Andrew          89.6            91.38   A-      89 (1.78 pts)
Emma            85.6            90.94   A-      89 (5.34 pts)
Logan           91.2            93.12   A       96 (1.92 pts)
```

## Check your work

To validate that your code satisfies the specified requirements, complete the following steps:

1. Use Visual Studio Code to build and run your app.

1. Verify that your application creates the following output:

```Output
Student         Exam Score      Overall Grade   Extra Credit

Sophia          92.2            95.88   A       92 (3.68 pts)
Andrew          89.6            91.38   A-      89 (1.78 pts)
Emma            85.6            90.94   A-      89 (5.34 pts)
Logan           91.2            93.12   A       96 (1.92 pts)
```

Congratulations if you succeeded in this challenge!
