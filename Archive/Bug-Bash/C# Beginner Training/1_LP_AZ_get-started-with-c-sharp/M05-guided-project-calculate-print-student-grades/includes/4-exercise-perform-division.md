In this exercise, you will calculate and store the average of the assignment scores from each student. Since we know the number of scored assignments for each student, the average is calculated by dividing the sum of the assignment scores by the number of assignments. To store the averages, we will be using the Decimal data type.

## Create variables to store the average

In this task, we will create a variable for each student that can be used to store the average score for their graded assignments.

1. In the .NET Editor, locate the Console.WriteLine() statements that are used to display each student's summed scores.

1. Create a blank code line above the the Console.WriteLine() statements.

1. On the blank code line that you just created, to declare the Decimal variables that will be used for the students current scores, enter the following code:

    ```c#
    decimal sophiaScore;
    decimal andrewScore;
    decimal emmaScore;
    decimal loganScore;

    ```

    Notice that we are only declaring the `decimal` variables and not initializing them. We choose the `decimal` type because we are representing an average grade and want to include a decimal place that would not be available if we used an integer. This way, we can see if a student made a score of 89.9 and bump them up from a B to an A.

    In the previous exercise, we initialized the Integer variables so that we could immediately use them in our console output. In this case, these Decimal variables will be initialized on the next step using calculations with our existing data, starting with Sophia's score.

1. To assign Sophia's current score in the class to the decimal `sophiaScore`, enter the following code: 

    ```c#
    sophiaScore = sophiaSum / currentAssignments;

    ```

    To calculate a student's the current score for the class, we divide the sum of assignment scores by the total number of assignments. Each student in the class has 5 assignments, represented by `currentAssignments` that we initialized during setup.

1. To assign the rest of the students' scores, enter the following code:

    ```c#
    andrewScore = andrewSum / currentAssignments;
    emmaScore = emmaSum / currentAssignments;
    loganScore = loganSum / currentAssignments;

    ```

    Utlimately, we want to print the grades of each student in this application. In the next step, we will modify the code to print each student's score rather than their assignment sum.

1. To print each student's current score, replace the sum variables in the print statements with the score variables:

    ```c#
    Console.WriteLine("Sophia: " + sophiaScore);
    Console.WriteLine("Andrew: " + andrewScore);
    Console.WriteLine("Emma: " + emmaScore);
    Console.WriteLine("Logan: " + loganScore);

    ``` 

1. Take a minute to consider the incremental approach that we are using to develop this application.

    Breaking down a problem into to smaller pieces is an important skill for developers. Building our code incrementally and checking our work frequently allows us to quickly develop reliable applications. In this case we are able to repurpose the WriteLine() method to verify that our code (our calculations) as we complete each stage in our process. 

1. To view the values of each student's current grade, select **Run**.
 
1. Notice that the scores are displayed as integers rather than decimals.

    You may recall that we examined calculations that include a mix of decimal and integer variables during a previous module. We learned that when we want the result of a division calculation to be a decimal value, either the dividend or divisor must be of type decimal (or both). We also learned that when we use integer variables in the calculation, we need to apply a technique know as casting to "convert" an integer to a decimal. 

    For our score calculation, we can obtain a decimal result by casting either the sum variable or `currentAssignments` as a decimal type. In this case we will cast the sum as a decimal. 

1. In our division operations, to cast an integer variable as a decimal, update your code as follows:

    ```c#
    sophiaScore = (decimal) sophiaSum / currentAssignments;
    andrewScore = (decimal) andrewSum / currentAssignments;
    emmaScore = (decimal) emmaSum / currentAssignments;
    loganScore = (decimal) loganSum / currentAssignments;
    ```

    We only need the dividend or divisor to be a decimal type for the division to result in a decimal value. Here we cast only the sum variable that's used as the dividend.

1.  Review the following grading scale that the teacher uses to assign letter grades:

    ```
    97 - 100	A+
    93 - 96 	A
    90 - 92	    A-
    87 - 89	    B+
    83 - 86	    B
    ```

    Our next step is to include a letter grade for each student based on their total score. Adding the letter grade to the displayed output will be a manual process. 

1. To determine the value of each student's current grade, select **Run**.

    Use the current grade for each student to determine the appropriate letter grade, rounding up or down as necessary.

1. To append letter grade after each student's numeric score, update your code as follows:

    ```c#
    Console.WriteLine("Sophia: " + sophiaScore + " A");
    Console.WriteLine("Andrew: " + andrewScore + " B");
    Console.WriteLine("Emma: " + emmaScore + " B");
    Console.WriteLine("Logan: " + loganScore + " A");
    ``` 

## Check Your Work

In this task, we will run the code and verify that the output is correct.

1. To run your code and display the student scores with letter grades, select **Run**.

1. To verify that your code is working as expected, compare the output of your application with the following:

    ```
    Sophia: 94.6 A
    Andrew: 83.6 B
    Emma: 83.4 B
    Logan: 95.4 A
    ```

    You code should now be displaying the student scores as a decimal value, and you should see the letter grade that you assigned.

    If your code displays different results, you will need to review your code to find your error and make updates. Run the code again to see if you have fixed the problem. Continue updating and running your code until your code produces the expected results.
    