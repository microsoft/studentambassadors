---
title: Prepare
durationInMinutes: 3
---
You'll be using Visual Studio Code to develop portions of a C# console application. You will be writing the code that performs various numeric calculations within a series iteration and selection statements. The values must be calculated within the existing iteration and selection structures. Here, we'll discuss the overall goals of the project and how you'll build and test your application. We'll also cover how to set up your development environment, including a "Starter" code project.

## Project specification

The Starter code project for this module is a C# console application that implements the following code features:

- Uses arrays to store student names and assignment scores.
- Uses a `foreach` statement to iterate through the student names as an outer program loop.
- Uses an `if` statement within the outer loop to identify the current student name and access that student's assignment scores.
- Uses a `foreach` statement within the outer loop to iterate through the assignment scores array and sum the values.
- Uses an algorithm within the outer loop to calculate the average exam score for each student.
- Use an `if-elseif-else` construct within the outer loop to evaluate the average exam score and assign a letter grade automatically.
- Integrates extra credit scores when calculating the student's final score and letter grade as follows:

    - Detects extra credit assignments based on the number of elements in the student's scores array.
    - Applies a 10% weighting factor to extra credit assignments before adding extra credit scores to the sum of exam scores.

Your goal in this challenge is to implement the coding updates required to produce the teacher's requested score report.

The current score report lists the student name followed by the calculated overall grade and letter grade. The existing report is formatted as follows:

```Output
Student         Grade   Letter Grade

Sophia          95.6    A
Andrew          91.6    A-
Emma            89.2    B+
Logan           93      A
```

In addition to the student's final numeric score and letter grade, the teacher wants the updated report to include the exam score and the impact that extra credit work has on the student's final grade. The format of the updated score report should appear as follows:

```Output
Student         Exam Score      Overall Grade   Extra Credit

Sophia          92.2            95.88   A       92 (3.68 pts)
Andrew          89.6            91.38   A-      89 (1.78 pts)
Emma            85.6            90.94   A-      89 (5.34 pts)
Logan           91.2            93.12   A       96 (1.92 pts)
```

## Setup

Use the following steps to prepare for the Guided project exercises.

1. Notice that the GitHub repo for this Module includes the following folders:

    The **M07-challenge-project-arrays-iteration-selection** folder contains the following folders:

    ```Output
    includes
    LabFiles
    media
    ```

    The **includes** and **media** folders contain the training materials.

    The **LabFiles** folder contains console applications related to this Guided project module. The **Starter** folder contains the code that you will start with for this coding project. The **Final** folder contains the solution code. You should not need the solution code to finish the Guided project.

1. Use Visual Studio Code to create a new console app.

1. Open the **LabFiles** folder, and then open the **Starter** folder.

    The **Starter** folder contains a Program.cs file.

1. Copy the contents of the Program.cs file to the clipboard.

1. Switch to the new console application that you created, and then open the Program.cs file.

    The default Program.cs file is a Hello World app.

1. Replace the contents of your Program.cs file with the file that you copied to the clipboard.

You're now ready to begin the Challenge project exercises. Good luck!
