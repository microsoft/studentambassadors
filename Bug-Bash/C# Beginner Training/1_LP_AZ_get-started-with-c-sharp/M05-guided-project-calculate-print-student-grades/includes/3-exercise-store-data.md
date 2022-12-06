In this exercise, you will use the assignment scores for each student to calculate their current grade in the class. To do this, you will first sum the values of their assignment scores, and then calculate their average score (their current grade). Let's get started.

> [!IMPORTANT]
> You need to have completed the Setup instructions in the previous unit, Prepare, before you begin this Exercise. 

## Create variables to store the sum

In this task, we will create a variable for each student that will represent the sum of their assignment scores. We will also display the student's sum along with their name in the console output. Since the assignment scores are represented as Integers, we will create Integer variables to store the sums.

1. Ensure that you have the .NET Editor open, and that you have the variables instantiated with each student's assignment scores.

    In the Prepare unit for this Guided project module, the Setup instructions have you copy student assignment scores in to the editor. If necessary, go back and complete the Setup instructions.

1. Scroll down to the bottom of your code and create a new blank code line.

1. To declare an Integer variable for each student that we can use to sum their scores, enter the following code:

    ```c#
    int sophiaSum = 0;
    int andrewSum = 0;
    int emmaSum = 0;
    int loganSum = 0;

    ```

    Notice that we have chosen to assign values to our variables as part of the declaration statement. Although value assignment is not required when declaring variables, it can make our code more efficient, which is the case here. Our next step to display output, and since that output will include a reference to these variables, they must be initialized.  

1. To create `Console.WriteLine()` statements that display the student name and the value of their summed assignment scores, enter the following code: 

    ```c#
    Console.WriteLine("Sophia: " + sophiaSum);
    Console.WriteLine("Andrew: " + andrewSum);
    Console.WriteLine("Emma: " + emmaSum);
    Console.WriteLine("Logan: " + loganSum);

    ```

    Utlimately, we will want display the student's current overall grade, but for now let's use these Console.WriteLine statements to display the value of our sum calculations. That way we can check to see if our code is working correctly at each stage of our development process.

    > [!NOTE]
    > More advanced developer environments, such as Visual Studio Code, provide tools that enable developers observe the values of application variables while their code is running. Learning how to use those tools saves professional developers lots of time during development. For now though, we can use Console.WriteLine() to help us verify that our code is working as expected.

1. In the .NET Editor, to run your code, select the green **Run** button.

1. Notice that we have no problem displaying our integer values, all 0s for now, using the same WriteLine() method that displays the string literals (student names).

    We saw this the first module of this Learning Path. The current numeric value is automatically retrieved by referencing the variable name.

    Now that we have the Console.WriteLine() statements ready to display our results, let's start adding the code that performs our calculations.

    > [!IMPORTANT]
    > We need to write the code that does the calculations above the code that displays the output.
 
1. Scroll up in the .NET Editor to a code line above to first Console.WriteLine() statement and create a new blank code line.

    Next, we are going to write the code that calculates the sum value for each student. To do this we will add the students' assignment scores and assign the value to the "sum" variables. We will start with Sophia. Her scores are as follows:

1. On the blank code line that you just created, enter the following code:

    ```c#
    sophiaSum = sophia1 + sophia2 + sophia3 + sophia4 + sophia5;

    ```

1. In the .NET Editor, select **Run**.

    Your output should now show that Sophia's sum is equal to 473. The others will still be 0.

1. Create a blank code line below the line used to assign the value to `sophiaSum`.

    We will add a similar sum calculation for the rest of the students.

1. Starting on the blank code line that you just created, enter the following code: 

    ```c#
    andrewSum = andrew1 + andrew2 + andrew3 + andrew4 + andrew5;
    emmaSum = emma1 + emma2 + emma3 + emma4 + emma5;
    loganSum = logan1 + logan2 + logan3 + logan4 + logan5;

    ```

## Check your work

In this task, we will run the code and verify the output is correct.

1. In the .NET Editor, select **Run**.

1. Review your output and verify that the sums of the assignment scores are correct:

    ```
    Sophia: 473
    Andrew: 418
    Emma: 417
    Logan: 477
    ```

    If your code displays different results, you will need to review your code to find your error and make updates. Run the code again to see if you have fixed the problem. Continue updating and running your code until your code produces the expected results.
