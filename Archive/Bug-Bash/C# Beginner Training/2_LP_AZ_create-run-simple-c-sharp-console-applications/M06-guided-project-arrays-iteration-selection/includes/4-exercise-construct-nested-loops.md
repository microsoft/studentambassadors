---
title: Exercise - Construct a nested loop structure for student grade calculations
durationInMinutes: 3
---

In this exercise, you'll add a string array to hold the student names, and then implement a nested `foreach` structure that iterates through names in an outer loop and scores in the inner loop. You'll begin by constructing the `studentNames` array and a `foreach` loop that iterates through the array elements. Next, you'll move the code that's used to calculate Sophia's grades into the code block of the "names" loop. Finally, you'll implement the code logic that uses the student's name to access their scores array, calculate their average score, and write their grade to the console. The detailed tasks that you'll complete during this exercise are:

1. Create names array: Create a student names array.

1. Create outer loop: Create a `foreach` loop that iterates through the student names.

1. Develop outer loop code block: Relocate the code that calculates and reports Sophia's score, placing it in the code block of the "names" loop.

1. Update calculations and reporting: Update the code that performs student score calculations using a new scores array.

> [!IMPORTANT]
> You need to have completed this module's previous Exercise, "Create arrays and foreach loops", before you begin this Exercise.

## Create a student names array and outer foreach loop

In this task, we'll create a student names array and a `foreach` loop that iterates through the student names.

1. Ensure that you have the Program.cs file open in the Visual Studio Code Editor.

1. Scroll to the top of your code file, and then locate the code lines that are used to declare the scores arrays.

1. Create a blank code line below the declaration of the scores arrays.

    Your blank code line should be located between the lines used to declare the scores arrays and the line used to declare `sophiaSum`.

1. To create a string array named `studentNames` that holds the names of the students, enter the following code:

    ```csharp
    // Student names
    string[] studentNames = new string[] { "Sophia", "Andrew", "Emma", "Logan" };
    ```

    Notice that we specify the student names as part of the declaration.

1. To create a `foreach` statement that we can use to iterate through the student names, enter the following code:

    ```csharp
    foreach (string name in studentNames)
    {
    }
    ```

1. To verify that our `foreach` loop is iterating through the `studentNames` array as intended, update the code block of the `foreach` statement as follows:

    ```csharp
    foreach (string name in studentNames)
    {
        Console.WriteLine($"{name}");

    }
    ```

1. Take a minute to review the code that you've created.

    ```csharp
    // Student names
    string[] studentNames = new string[] { "Sophia", "Andrew", "Emma", "Logan" };
    
    foreach (string name in studentNames)
    {
        Console.WriteLine($"{name}");

    }
    ```

    Our code will be using this `foreach` loop as the outer loop of our application. By the end of this exercise, we intend to implement the following logic in our app:

    For each of the students in the `studentNames` array:

    - determine the current student
    - access the current student's scores
    - calculate the current student's grade (sum and average)
    - write the current student's grade to the console

    For now however, we will only be writing the names of the students to the console.  

1. On the Visual Studio Code **File** menu, click **Save**.

1. In the Visual Studio Code EXPLORER panel, right-click **Starter**, and then select **Open in Integrated Terminal**.

    > [!IMPORTANT]
    > The Terminal command prompt must be displaying the folder path for your Program.cs file.

1. At the Terminal command prompt, type **dotnet build** and then press Enter.

    The `dotnet build` command instructs the compiler to build the application. If any errors are detected, they will be reported.

1. If you see Error or Warning messages, you need to fix them before continuing.

1. At the Terminal command prompt, type **dotnet run** and then press Enter.

1. Verify that your code produced the following output:

    ```Output
    Sophia
    Andrew
    Emma
    Logan
    Student         Grade
    
    Sophia:         92.2    A-
    Press the Enter key to continue
    ```

    > [!NOTE]
    > If you don't see the list of student names above Sophia's score report, go back and verify that you entered your code correctly.

1. In the TERMINAL panel, to stop your running application, press the Enter key.

1. Close the Terminal panel.

## Calculate Sophia's score inside the outer names loop

In this task, we'll relocate the code that calculates and reports Sophia's score, placing it in the code block of the "names" loop.

1. In the Visual Studio Code Editor, locate the code lines that are used to calculate and report Sophia's grade.

    ```csharp
    int sophiaSum = 0;
    
    decimal sophiaScore;
    
    foreach (int score in sophiaScores)
    {
        // add the exam score to the sum
        sophiaSum += score;
    
    }
    
    sophiaScore = (decimal)sophiaSum / currentAssignments;
    
    Console.WriteLine("Student\t\tGrade\n");
    Console.WriteLine("Sophia:\t\t" + sophiaScore + "\tA-");
    ```

    > [!NOTE]
    > Our next step will be to move this code from its current location to the code block of the "names" `foreach` loop.

1. Use a cut-and-paste operation to move the code that calculates and reports Sophia's grade to the code block of the "names" `foreach` loop.

    If you're unsure how to cut-and-paste in Visual Studio Code, try the approach described in the following steps:

    1. Select the code that's used to calculate and report Sophia's grade.

        You can click-and-drag to select code lines.

    1. On the Visual Studio Code **Edit** menu, select **Cut**.

    1. In the Visual Studio Code Editor, position the cursor on the blank code line below the following code: `Console.WriteLine($"{name}");`

    1. On the Visual Studio Code **Edit** menu, select **Paste**.

1. Update your code to display proper code line indentation.

    > [!HINT]
    > Visual Studio Code provides a `Format Document` command that can be used to keep your code formatting updated. Right-click inside the Visual Studio Code Editor panel, and then select **Format Document** from the popup menu. The keyboard shortcut for this command is: `Shift + Alt + F`.

1. Ensure that your updates match the following code:

    ```csharp
    // Student names
    string[] studentNames = new string[] { "Sophia", "Andrew", "Emma", "Logan" };
    
    foreach (string name in studentNames)
    {
        Console.WriteLine($"{name}");
        int sophiaSum = 0;
    
        decimal sophiaScore;
    
        foreach (int score in sophiaScores)
        {
            // add the exam score to the sum
            sophiaSum += score;
    
        }
    
        sophiaScore = (decimal)sophiaSum / currentAssignments;
    
        Console.WriteLine("Student\t\tGrade\n");
        Console.WriteLine("Sophia:\t\t" + sophiaScore + "\tA-");
    }

    Console.WriteLine("Press the Enter key to continue");
    Console.ReadLine();
    ```

    Notice that at this point, our code will calculate and report Sophia's score regardless of the `name` of the current student. We will address that shortly.

1. Delete the following code:

    ```csharp
    Console.WriteLine($"{name}");
    ```

1. On the blank code line that you just created, enter the following code:

    ```csharp
    if (name == "Sophia")
    {    
    ```

1. Create a blank code line after the code that's used to write Sophia's grade to the console.

1. To close the code block of the `if` statement, enter the following code:

    ```csharp
    }    
    ```

1. Update your code to display proper code line indentation.

    > [!HINT]
    > Visual Studio Code provides a `Format Document` command that can be used to keep your code formatting updated. Right-click inside the Visual Studio Code Editor panel, and then select **Format Document** from the popup menu. The keyboard shortcut for this command is: `Shift + Alt + F`.

1. Take a minute to review your code.

    Your code should match the following code:

    ```csharp
    using System;
    
    // initialize variables - graded assignments 
    int currentAssignments = 5;
    
    int[] sophiaScores = new int[] { 90, 86, 87, 98, 100 };
    int[] andrewScores = new int[] { 92, 89, 81, 96, 90 };
    int[] emmaScores = new int[] { 90, 85, 87, 98, 68 };
    int[] loganScores = new int[] { 90, 95, 87, 88, 96 };
    
    // Student names
    string[] studentNames = new string[] {"Sophia", "Andrew", "Emma", "Logan"};
    
    foreach (string name in studentNames)
    {
        if (name == "Sophia")
        {
            foreach (int score in sophiaScores)
            {
                // add the exam score to the sum
                sophiaSum += score;
            }
    
            sophiaScore = (decimal)(sophiaSum) / currentAssignments;
    
            Console.WriteLine("Student\t\tGrade\n");
            Console.WriteLine("Sophia:\t\t" + sophiaScore + "\tA-");
        }
    }
    
    Console.WriteLine("Press the Enter key to continue");
    Console.ReadLine();
    ```

    Notice that the `if` statement inside our outer `foreach` code block limits which student's grade is calculated and reported. This isn't exactly what we need, but it is a step in the right direction.

1. On the Visual Studio Code **File** menu, click **Save**.

1. In the Visual Studio Code EXPLORER panel, right-click **Starter**, and then select **Open in Integrated Terminal**.

    > [!IMPORTANT]
    > The Terminal command prompt must be displaying the folder path for your Program.cs file.

1. At the Terminal command prompt, type **dotnet build** and then press Enter.

    The `dotnet build` command instructs the compiler to build the application. If any errors are detected, they will be reported.

1. If you see Error or Warning messages, you need to fix them before continuing.

1. At the Terminal command prompt, type **dotnet run** and then press Enter.

1. Verify that your code produced the following output:

    ```Output
    Student         Grade
    
    Sophia:         92.2    A-
    ```

    > [!NOTE]
    > If you still see the list of student names displayed above Sophia's score report, make sure that you saved your updates.

1. In the TERMINAL panel, to stop your running application, press the Enter key.

1. Close the Terminal panel.

## Update the nested loop to calculate all student scores

In this task, we'll update the code that performs student score calculations using a new scores array. We'll begin by creating an array named `studentScores` that can be used to hold the scores of any student. Next, we'll create an `if-elseif` construct that uses the current student's name to assign their scores array to `studentScores`. Finally, we'll update code that calculates and reports the student's grades. When we're done, the report should include the name and numeric score for all students.

1. Create a blank code line below the declaration of the `studentNames` array.

    The blank line should be above the outer  `foreach` statement.

1. To create an integer array that we can use to hold the scores of the current student, enter the following code:

    ```csharp
    int[] studentScores = new int[10];

    ```

    Notice that we don't assign any values to the array at this point. We specify that the array can contain 10 elements.

1. Create a blank code line at the top of the outer `foreach` code block.

    The blank line should be inside the `foreach` code block and above the `if` statement that evaluates whether `name` is equal to Sophia.

1. To create a string variable that will be used to hold the name of the current student, enter the following code:

    ```csharp
    string currentStudent = name;

    ```

    > [!NOTE]
    > We could continue to use `name` to track the name of the current student as we iterate through the names array, but using `currentName` will make it easier to understand our code logic as we build out our application in the upcoming steps.

1. To substitute `currentStudent` for `name` in the `if` statement that evaluates whether `name` is equal to Sophia, update your code as follows:

    ```csharp
    if (currentStudent == "Sophia")
    ```

1. Move the code that calculates and reports Sophia's score to a location below the code block.

    You are moving all of the code that's in the code block to a location below the code block. The reason for doing this will become apparent during the next few steps.

1. Verify that the code in your outer `foreach` code block matches the following code:

    ```csharp
    {
        string currentStudent = name;
    
        if (currentStudent == "Sophia")
        {
        }
    
        int sophiaSum = 0;

        decimal sophiaScore;

        foreach (int score in sophiaScores)
        {
            // add the exam score to the sum
            sophiaSum += score;

        }

        sophiaScore = (decimal)sophiaSum / currentAssignments;

        Console.WriteLine("Student\t\tGrade\n");
        Console.WriteLine("Sophia:\t\t" + sophiaScore + "\tA-");
        
    }
    ```

1. To assign the `sophiaScores` array to `studentScores` when `currentStudent == "Sophia"`, update your `if` statement code as follows:

    ```csharp
    if ()
        studentScores = sophiaScores;

    ```

    Notice that we've removed the curly braces from the `if` statement code block during this code update.

1. To add an `else if` statement that assigns the `andrewScores` array to `studentScores` when `currentStudent == "Andrew"`, enter the following code:

    ```csharp
    else if (currentStudent == "Andrew")
        studentScores = andrewScores;

    ```

1. Create another `else if` statement to assign the `emmaScores` array to `studentScores` when `currentStudent == "Emma"`.

1. Create an `else` statement to assign the `loganScores` array to `studentScores` when `currentStudent == "Logan"`.

1. Ensure that your `foreach` code block matches the following code:

    ```csharp
    foreach (string name in studentNames)
    {
        string currentStudent = name;
    
        if (currentStudent == "Sophia")
            studentScores = sophiaScores;
        
        else if (currentStudent == "Andrew")
            studentScores = andrewScores;
    
        else if (currentStudent == "Emma")
            studentScores = emmaScores;
    
        else if (currentStudent == "Logan")
            studentScores = loganScores;
    
        int sophiaSum = 0;

        decimal sophiaScore;

        foreach (int score in sophiaScores)
        {
            // add the exam score to the sum
            sophiaSum += score;

        }

        sophiaScore = (decimal)sophiaSum / currentAssignments;

        Console.WriteLine("Student\t\tGrade\n");
        Console.WriteLine("Sophia:\t\t" + sophiaScore + "\tA-");
        
    }
    ```

    Next, we need to update the inner `foreach` loop to use `studentScores` "depersonalize" the variables we use in our calculations.

1. To substitute `studentScores` for `sophiaScores` in the `foreach` loop that iterates through the scores array, update your code as follows:

    ```csharp
    foreach (int score in studentScores)
    ```

1. To replace the Sophia-specific variable declarations with more generic names, update your code as follows:

    ```csharp
    int sumAssignmentScores = 0;

    decimal currentStudentGrade = 0;
    ```

    These two variable declarations are intended to replace the following Sophia-specific variable declarations:

    ```csharp
    int sophiaSum = 0;

    decimal sophiaScore;
    ```

1. To apply the new variable name to our equation used to sum student scores, update your inner `foreach` code block as follows:

    ```csharp
    foreach (int score in studentScores)
    {
        // add the exam score to the sum
        sumAssignmentScores += score;
    }
    ```

1. To apply the new variable name to the equation used for calculate the average score, update your code as follows:

    ```csharp
    currentStudentGrade = (decimal)(sumAssignmentScores) / currentAssignments;
    ```

1. Take a minute to review your code.

    ```csharp
    int[] studentScores = new int[10];
    
    foreach (string name in studentNames)
    {
        string currentStudent = name;
    
        if (currentStudent == "Sophia")
            studentScores = sophiaScores;
        
        else if (currentStudent == "Andrew")
            studentScores = andrewScores;
    
        else if (currentStudent == "Emma")
            studentScores = emmaScores;
    
        else if (currentStudent == "Logan")
            studentScores = loganScores;
    
        // initialize/reset the sum of scored assignments
        int sumAssignmentScores = 0;
    
        // initialize/reset the calculated average of exam + extra credit scores
        decimal currentStudentGrade = 0;
        
        foreach (int score in studentScores)
        {
            // add the exam score to the sum
            sumAssignmentScores += score;
        }
    
        currentStudentGrade = (decimal)(sumAssignmentScores) / currentAssignments;
    
        Console.WriteLine("Student\t\tGrade\n");
        Console.WriteLine("Sophia:\t\t" + sophiaScore + "\tA-");
        
    }
    ```

    Our nested `foreach` loops will now iterate through the student names and use the student's scores to calculate their grades, but we still need to update the code used to generate the score report.

1. To print the student name and calculate score to the console, update the second `Console.WriteLine` statement as follows:

    ```csharp
    Console.WriteLine($"{currentStudent}\t\t{currentStudentGrade}\t?");
    ```

    Notice that we replaced the letter grade assignment with a "?". We will work on automating the assignment of letter grades in the next exercise.

1. Move the `Console.WriteLine` statement that's used to write the column labels of our score report to location just above the outer `foreach` loop.

    We don't want to repeat the column headers for each student score, so we move this code to a point above the outer `foreach` loop.

1. On the Visual Studio Code **File** menu, click **Save**.

1. Take a minute to review your application code.

    Your full application should now match the following code:

    ```csharp
    using System;
    
    // initialize variables - graded assignments 
    int currentAssignments = 5;
    
    int[] sophiaScores = new int[] { 90, 86, 87, 98, 100 };
    int[] andrewScores = new int[] { 92, 89, 81, 96, 90 };
    int[] emmaScores = new int[] { 90, 85, 87, 98, 68 };
    int[] loganScores = new int[] { 90, 95, 87, 88, 96 };
    
    // Student names
    string[] studentNames = new string[] { "Sophia", "Andrew", "Emma", "Logan" };
    
    int[] studentScores = new int[10];
    
    // Write the Report Header to the console
    Console.WriteLine("Student\t\tGrade\n");
    
    foreach (string name in studentNames)
    {
        string currentStudent = name;
    
        if (currentStudent == "Sophia")
            studentScores = sophiaScores;
        
        else if (currentStudent == "Andrew")
            studentScores = andrewScores;
    
        else if (currentStudent == "Emma")
            studentScores = emmaScores;
    
        else if (currentStudent == "Logan")
            studentScores = loganScores;
    
        // initialize/reset the sum of scored assignments
        int sumAssignmentScores = 0;
    
        // initialize/reset the calculated average of exam + extra credit scores
        decimal currentStudentGrade = 0;
        
        foreach (int score in studentScores)
        {
            // add the exam score to the sum
            sumAssignmentScores += score;
        }
    
        currentStudentGrade = (decimal)(sumAssignmentScores) / currentAssignments;
    
        Console.WriteLine($"{currentStudent}\t\t{currentStudentGrade}\t?");
    }
    ```

    With the code that generates the student's score report updated, it appears that we're ready to check our work.

## Check your work

In this task, we'll run the application to verify that our code logic is working as expected.

1. Ensure that you've saved your changes to the Program.cs file.

1. In the Visual Studio Code EXPLORER panel, right-click **Starter**, and then select **Open in Integrated Terminal**.

1. At the Terminal command prompt, type **dotnet build** and then press Enter.

1. If you see Error or Warning messages, you need to fix them before continuing.

1. At the Terminal command prompt, type **dotnet run** and then press Enter.

1. Verify that your code produced the following output:

    ```Output
    Student         Grade
    
    Sophia          92.2    ?
    Andrew          89.6    ?
    Emma            85.6    ?
    Logan           91.2    ?
    Press the Enter key to continue
    ```

1. In the TERMINAL panel, to stop your running application, press the Enter key.

1. Close the Terminal panel.

Congratulations, your application has come a long way from where you started out. You are making efficient use of arrays and `foreach` iterations, and you've integrated an `if` statement that enables your code to select the correct scores array.
