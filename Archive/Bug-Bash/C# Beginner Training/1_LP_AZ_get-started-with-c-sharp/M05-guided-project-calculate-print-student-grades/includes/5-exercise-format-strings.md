In this exercise, you will modify the console output from the previous exercise to achieve the reporting format specified by the teacher.

## Format the console output

In this task, we will update our code to apply the finishing touches to our reported output. We will start by adding a header row that includes the column labels specified by the teacher. After that, we will use character escape sequences to add additional padding between the columns of information.

1. In the .NET Editor, locate the Console.WriteLine() statements that are used to display each student's current class score and letter grade.

1. Create a blank code line above the the Console.WriteLine() statements.

1. On the blank code line that you just created, to add a header for the student grades, enter the following code:

    ```c#
    Console.WriteLine("Student Grade\n");
    ```

    Notice that we are including `\n` at the end of the text. In our "Perform basic string formatting with C#" module, we learned that the `\n` escape character sequence will cause a new line to be created. The location of the escape sequence is important. In this case, the `\n` is at the end of information that we want to write to the console, so the new line will be added after "Student Grade" is displayed. 

1. To format our output as aligned columns of text, replace the spaces between words with the `\t` escape sequence as follows:

    ```c#
    Console.WriteLine("Student\tGrade\n");
    Console.WriteLine("Sophia:\t" + sophiaScore + "\tA");
    Console.WriteLine("Andrew:\t" + andrewScore + "\tB");
    Console.WriteLine("Emma:\t" + emmaScore + "\tB");
    Console.WriteLine("Logan:\t" + loganScore + "\tA");
    ```

    The `\t` escape sequence will insert a tab stop between the text items. This should result in left-aligned columns of information.

1. To view the results of your updates, select **Run**.

1. Compare your output with the following:

    ```Output
    Student	Grade

    Sophia:	94	A
    Andrew:	83	B
    Emma:	83	B
    Logan:	95	A
    ```

1. Notice that despite using a tab instead of a space character, some lines still don't have much whitespace between the student's name and their numeric score.

    This is due to the way that tab spacing is applied. Tab stop locations are set at 4 character intervals and each tab will advanced to the next tab stop location. If we have a string of 5 characters followed by a tab escape sequence, the escape sequence will advance to the tab stop at the 8 character location, filling the gap with space characters to create whitespace in our output. However, we will advance to the same location if we have a string of 7 characters followed by a tab escape sequence. This creates the column alignment that we want, but it also means that tab escape sequences are more noticeable when they occur further from the next tab stop location.

1. To make the whitespace more noticeable between the first two columns, add an additional `\t` after the student names as follows:

    ```c#
    Console.WriteLine("Student\t\tGrade\n");
    Console.WriteLine("Sophia:\t\t" + sophiaScore + "\tA");
    Console.WriteLine("Andrew:\t\t" + andrewScore + "\tB");
    Console.WriteLine("Emma:\t\t" + emmaScore + "\tB");
    Console.WriteLine("Logan:\t\t" + loganScore + "\tA");
    ```

## Check Your Work

In this task, we will run the code and verify that the output is correct.

1. To run your code and display the formatted output, select **Run**.

1. To verify that your code is working as expected, compare the output of your application with the following:

    ```Output
    Student		Grade

    Sophia:		94	A
    Andrew:		83	B
    Emma:		83	B
    Logan:		95	A
    ```

    If your code displays different results, you will need to review your code to find your error and make updates. Run the code again to see if you have fixed the problem. Continue updating and running your code until your code produces the expected results.
