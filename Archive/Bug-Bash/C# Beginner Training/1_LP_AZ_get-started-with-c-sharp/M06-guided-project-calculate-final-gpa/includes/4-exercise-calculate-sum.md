In this exercise, you will calculate and store the total number of credit hours as well as the total grade points earned for each course. These values will later be used to calculate the GPA. Since both the credit hours and grade values are represented as whole numbers, we will store the sums using the Integer data type.

## Create variables to store the average

Recall that to calculate a student's GPA, we need the total number of credit hours, and the total number of grade points earned. The grade points earned for a course is equal to the product of the number of credit hours for that course and numeric grade value earned. For example:

```
Course          Credit  Credit Hours    Grade Points
English 101     4		3               12
``` 

In this task, we will create the variables to store values that are needed to calculate the GPA. We will create a variable to store the sum of the total credit hours for each course, and another variable to store the sum of the grade points the student earned for each course.

1. In the .NET Editor, locate the Console.WriteLine() statements that are used to display the course information.

1. Create a blank code line above the the Console.WriteLine() statements.

1. On the blank code line that you just created, to create a variable that will store the total number of credit hours, enter the following code:

    ```c#
    int totalCreditHours = 0;

    ```

    Notice that we are initializing the total to 0. This will allow us to increment the sum while keeping our code organized.

1. To increment the sum to represent the total number of credit hours, enter the following code: 

    ```c#
    totalCreditHours += course1Credit;
    totalCreditHours += course2Credit;
    totalCreditHours += course3Credit;
    totalCreditHours += course4Credit;
    totalCreditHours += course5Credit;

    ```

1. To create a variable that will store the total number of grade points earned for each course, enter the following code:

    ```c#
    int totalGradePoints = 0;

    ```

1. To increment the sum by the grade points earned for the first course, enter the following code:

    ```c#
    totalGradePoints += course1Credit * course1Grade;

    ``` 

1. To increment the sum by the grade points earned for the remainder of the courses, enter the following code:

    ```c#
    totalGradePoints += course2Credit * course2Grade;
    totalGradePoints += course3Credit * course3Grade;
    totalGradePoints += course4Credit * course4Grade;
    totalGradePoints += course5Credit * course5Grade;

    ``` 

1. Take a minute to review your code.

    Notice that our code breaks the problem down into managable pieces rather than trying to calculate the GPA in one large operation. First we initialize and calculate the value of totalCreditHours, then we intialize and calculate the value of totalGradePoints. Afterwards, we will use these values in our final calculation. 

    Now that our code is calculating a value for totalGradePoints, let's verify that our calculations are correct before continuing. It's important to stop and check our work periodically. Checking your work at various stages will make it easier to locate any errors in your coding logic.

1. To print the values of `totalGradePoints` and `totalCreditHours`, enter the following code:

    ```c#
    Console.WriteLine($"{totalGradePoints} {totalCreditHours}");
    ```

    We can remove this WriteLine() statement later if it isn't needed.

## Check Your Work

In this task, we will run the code and verify that the output is correct.

1. To run your code and display the current values of `totalGradePoints` and `totalCreditHours`, select **Run**.

1. Verify that your output matches the following:

    ```
    57 17
    English 101 4 3
    Algebra 101 3 3
    Biology 101 3 4
    Computer Science I 3 4
    Psychology 101 4 3
    ```

    If your code displays different results, you will need to review your code to find your error and make updates. Run the code again to see if you have fixed the problem. Continue updating and running your code until your code produces the expected results.
