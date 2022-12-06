In this exercise, you will calculate the final GPA and modify the console output to achieve the desired reporting format. The GPA is equal to the sum of the total grade points divided by the sum of the total credit hours.

## Calculate the final GPA

1. In the .NET Editor, locate the Console.WriteLine() statements that are used to display the course information.

1. Remove the following code from the previous exercise:

    ```c#
    Console.WriteLine($"{totalGradePoints} {totalCreditHours}");
    ```

    Since we have verified our values are correct, this line is no longer needed.

1. Create a blank code line above the the Console.WriteLine() statements.

1. On the blank code line that you just created, to initialize a variable that will store the final GPA, enter the following code:

    ```c#
    decimal gradePointAverage = gradePointsSum/totalCreditHours;

    ```

1. Take a moment to consider the data types we are dividing. 

    We learned in a previous module that when we want the result of a division calculation to be a decimal value, either the dividend or divisor must be of type decimal (or both). We also learned that when we use integer variables in the calculation, we need to use the cast operator to temporarily convert an integer to a decimal. 

1. To retrieve a decimal value from the division, update your code to the following:

    ```c#
    decimal gradePointAverage = (decimal) gradePointsSum/totalCreditHours;

    ```

1. Navigate to the last Console.WriteLine() statement and create a new blank code line after the last statement.

1. To display the final GPA, enter the following code: 

    ```c#
    Console.WriteLine($"Final GPA: {gradePointAverage}");
    ```

1. To view the results, select **Run**.

    Compare your output with the following:

    ```
    English 101 4 3
    Algebra 101 3 3
    Biology 101 3 4
    Computer Science I 3 4
    Psychology 101 4 3
    Final GPA: 3.3529411764705882352941176471
    ```

1. Notice that our decimal result contains many more digits than a standard GPA value. In future modules, we will learn a variety of methods to shorten decimal values. For now, we will use the techniques we learned in previous modules to display the GPA correctly.

## Format the decimal output

In this task, we will manipulate the decimal GPA value so that only 3 digits are displayed.

Ultimately, we want to display the first digit of the GPA, a decimal point, followed by the first two digits after the decimal. We can achieve this by using two variables to store the leading and trailing digits respectively, and then printing them together using Console.WriteLine(). We can use operations to extract the leading and trailing digits.

1. Navigate to the top of the Console.WriteLine() statements.

1. Create a blank code line above the the Console.WriteLine() statements.

1. On the blank code line that you just created, to initialize a variable that will store the leading digit of the GPA, enter the following code:

    ```c#
    int leadingDigit = (int) gradePointAverage;

    ```

    Notice that to extract the leading digit from the decimal, we are casting it to an integer value. This is a simple and reliable method because casting a fractional value will never round up the result. Meaning if the GPA is 2.99, casting the decimal value to an int will result in 2.

1. To initialize a variable that will store the first two digits after the decimal, enter the following code:

    ```c#
    int trailingDigits = (int) (gradePointAverage * 100) - (leadingDigit * 100);
    ```

    In the first half of this operation, we are moving the decimal two digits to the right. In the second half, we are adding zeroes to the leading digit. Afterwards, we subtract the two and cast the result to an integer. Here is an example:

    Suppose `gradePointAverage = 2.994573` and `leadingDigit = 2`
    So the operation would result in the following:
    ```
    int trailingDigits = (int) (2.994573 * 100) - (2 * 100);
    int trailingDigits = (int) 299.4573 - 200;
    int trailingDigits = (int) 99.4573;
    ```
    And the resulting value of `trailingDigits` is 99;

1. To correct the final GPA output, update the last Console.WriteLine() statement to the following:

    ```c#
    Console.WriteLine($"Final GPA: {leadingDigit}.{trailingDigits}");
    ```

## Check Your Work

In this task, we will run the code and verify that the output is correct.

1. To run your code and display the formatted output, select **Run**.

1. To verify that your code is working as expected, compare the output of your application with the following:

    ```
    English 101 4 3
    Algebra 101 3 3
    Biology 101 3 4
    Computer Science I 3 4
    Psychology 101 4 3
    Final GPA: 3.35
    ```

    If your code displays different results, you will need to review your code to find your error and make updates. Run the code again to see if you have fixed the problem. Continue updating and running your code until your code produces the expected results.
    