---
title: Prepare
durationInMinutes: 3
---
You'll be using Visual Studio Code to develop a C# application that implements arrays, `foreach` statements, and `if` statements. You will be creating array variables that contain the input data for the application. You'll also be using `foreach` and `if` statements to develop a nested looping and branching structure that implements your application design goals.

## Project overview

You are developing a Student Grading application that automates the calculation of grades for each student in a class. The parameters for your application are:

- The application will be a C# console application.
- You start out with a short list of four students and their five exam scores.
- Each exam score is expressed as an integer value, 0-100, where 100 represents 100% correct.
- Final scores are calculated as an average of the five exam scores.
- Your application needs to accommodate extra credit assignments.

    - Extra credit scores must be included in the student's scores array.
    - Extra credit assignments will be worth 10% of an exam score when applied toward the final numeric grade.
    - Extra credit assignment scores must be added to the student's total exam score before calculating the final numeric grade.

- Your application needs to automatically assign letter grades based on the calculated final score for each student.
- Your application needs to output/display each student’s name and formatted grade.
- Your application needs to support adding additional students and scores with minimal impact to the code.

You have already completed an initial version of the application. The Starter code project for this Guided project module includes a Program.cs file that provides the following code features:

- The code declares variables used to define student names and individual exam scores for each student.
- The code includes the variables and algorithms used to sum the exam scores and calculate the average exam score for each student.
- The code includes a hard coded letter grade that the developer must apply manually.
- The code includes Console.WriteLine() statements to display the student grading report.

Your goal is to update the existing code to include the following features:

- Use arrays to store student names and assignment scores.
- Use a `foreach` statement to iterate through the student names as an outer program loop.
- Use an `if` statement within the outer loop to identify the current student name and access that student's assignment scores.
- Use a `foreach` statement within the outer loop to iterate through the assignment scores array and sum the values.
- Use an updated algorithm within the outer loop to calculate the average exam score for each student.
- Use an `if-elseif-else` construct within the outer loop to evaluate the average exam score and assign a letter grade automatically.
- Integrate extra credit scores when calculating the student's final score and letter grade as follows:

    - Your code must detect extra credit assignments based on the number of elements in the student's scores array.
    - Your code must apply the 10% weighting factor to extra credit assignments before adding extra credit scores to the sum of exam scores.

The following list shows the letter grade corresponding to numeric scores:

```Output
97 - 100   A+
93 - 96    A
90 - 92    A-
87 - 89    B+
83 - 86    B
80 - 82    B-
77 - 79    C+
73 - 76    C
70 - 72    C-
67 - 69    D+
63 - 66    D
60 - 62    D-
0  - 59    F
```

The application needs to produce a formatted student grading report that appears as follows:

```Output
Student         Grade

Sophia:         92.2    A-
Andrew:         89.6    B+
Emma:           85.6    B
Logan:          91.2    A-
```

## Setup

Use the following steps to prepare for the Guided project exercises.

1. Notice that the GitHub repo for this Module includes the following folders:

    The **M06-guided-project-arrays-iteration-selection** folder contains the following folders:

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

You are now ready to begin the Guided project exercises. Good luck!
