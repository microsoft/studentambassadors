In this exercise, you will modify the console output from the previous exercise to achieve the specified reporting format.

## Format the console output

In this task, we will update our code to apply the finishing touches to our reported output. We will start by including the student's name and adding a header row that includes the column labels. After that, we will use character escape sequences to add additional padding between the columns of information.

1. In the .NET Editor, locate the Console.WriteLine() statements that are used to display the student's course information.

1. Create a blank code line above the the Console.WriteLine() statements.

1. On the blank code line that you just created, to add the student's name, enter the following code:

    ```c#
    Console.WriteLine($"Student: {studentName}\n");

    ```

    Notice that we are including `\n` at the end of the text. In our "Perform basic string formatting with C#" module, we learned that the `\n` escape character sequence will cause a new line to be created. The location of the escape sequence is important. In this case, the `\n` is at the end of information that we want to write to the console, so the new line will be added after "Student Grade" is displayed. 

1. Create a blank code line  after the previous Console.WriteLine() statement.

1. On the blank code line that you just created, to add a header for course information, enter the following code:

    ```c#
    Console.WriteLine("Course\t\t\tGrade\tCredit Hours");

    ```

    Notice we are adding three tabs after the course name. This will allow extra space for longer course names.


1. To format our output as aligned columns of text, replace the spaces between words with the `\t` escape sequence as follows:
 
    ```c#
    Console.WriteLine($"{course1Name}\t\t\t{course1Grade}\t\t{course1Credit}");
    Console.WriteLine($"{course2Name}\t\t\t{course2Grade}\t\t{course2Credit}");
    Console.WriteLine($"{course3Name}\t\t\t{course3Grade}\t\t{course3Credit}");
    Console.WriteLine($"{course4Name}\t{course4Grade}\t\t{course4Credit}");
    Console.WriteLine($"{course5Name}\t\t{course5Grade}\t\t{course5Credit}");

    ```

    The `\t` escape sequence will insert a tab stop between the text items. This should result in left-aligned columns of information.

    Notice that we reduce the number of tabs for `course4Name` and `course5Name`. This is becaues these course names are longer than the others. In the previous step, we added additional tabs after the course name column to keep spacing consistent for both long and short course names.

1. To add padding to the final GPA result output, update the code as follows:

    ```c#
    Console.WriteLine($"\nFinal GPA:\t\t\t{leadingDigit}.{trailingDigits}");

    ```

## Check Your Work

In this task, we will run the code and verify that the output is correct.

1. To run your code and display the formatted output, select **Run**.

1. To verify that your code is working as expected, compare the output of your application with the following:

    ```
    Student: Sophia Johnson

    Course			Grade	Credit Hours	
    English 101			4		3
    Algebra 101			3		3
    Biology 101			3		4
    Computer Science I	3		4
    Psychology 101		4		3

    Final GPA:			3.35
    ```

    If your code displays different results, you will need to review your code to find your error and make updates. Run the code again to see if you have fixed the problem. Continue updating and running your code until your code produces the expected results.
    