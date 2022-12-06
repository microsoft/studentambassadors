In this exercise, we will begin setting up variables needed to calculate a student's GPA. Let's get started.

> [!IMPORTANT]
> You need to have completed the Setup instructions in the previous unit, Prepare, before you begin this Exercise. 

## Create variables to store the grade values

In this task, we will identify the numeric equivalents for the student's earned letter grade. Then we will declare variables to store the numeric grade value for each class. The numeric equivalents are represented as whole numbers, so we will be using the Integer data type to store the values.

1. Ensure that you have the .NET Editor open, and that you have the variables instantiated with each student's name, course names, and credit hours.

    In the Prepare unit for this Guided project module, the Setup instructions have you copy student course information into the editor. If necessary, go back and complete the Setup instructions.

1. Review the following letter grade numeric equivalent values
    A = 4 grade points
    B = 3 grade points
    C = 2 grade points
    D = 1 grade point
    F = 0 grade points

1. Scroll down to the bottom of your code and create a new blank line.

1. To declare an Integer variable for each numeric grade value, enter the following code:

    ```c#
    int gradeA = 4;
    int gradeB = 3;
    int gradeC = 2;
    int gradeD = 1;
    int gradeF = 0;

    ```

    Notice that we are using fixed values to represent each of the numeric grades. This will help make our code easy to understand and help to prevent typos if we need to enter different grades repeatedly.

1. Review the student's grades for each course:

    ```
    Course			    Grade		
    English 101		     A
    Algebra 101		     B
    Biology 101		     B
    Computer Science I	 B
    Psychology 101	     A
    ```

    We will be using this information to create variables that will store the numeric grade values for each course.

1. To create variables that will store the grades for each course, enter the following code: 

    ```c#
    int course1Grade = gradeA;
    int course2Grade = gradeB;
    int course3Grade = gradeB;
    int course4Grade = gradeB;
    int course5Grade = gradeA;

    ```

1. To display the course names along with the numeric grade, enter the following code:

    ```c#
    Console.WriteLine($"{course1Name} {course1Grade}");
    Console.WriteLine($"{course2Name} {course2Grade}");
    Console.WriteLine($"{course3Name} {course3Grade}");
    Console.WriteLine($"{course4Name} {course4Grade}");
    Console.WriteLine($"{course5Name} {course5Grade}");
    ```

1. In the .NET Editor, to run your code, select the green **Run** button.

    Your output should match the following:

    ```
    English 101 4
    Algebra 101 3
    Biology 101 3
    Computer Science I 3
    Psychology 101 4
    ```

    If your output does not match, be sure to check your variable names.

1. Take a moment to consider the current output and the final output of our application. 

    In the final output of our application, we want to display the class name, grade, and credit hours. This is a good time to add the credit hours in to our print statements.
 
1. To add the credit hours for each class to the print statements, update your code to the following:

    ```c#
    Console.WriteLine($"{course1Name} {course1Grade} {course1Credit}");
    Console.WriteLine($"{course2Name} {course2Grade} {course2Credit}");
    Console.WriteLine($"{course3Name} {course3Grade} {course3Credit}");
    Console.WriteLine($"{course4Name} {course4Grade} {course4Credit}");
    Console.WriteLine($"{course5Name} {course5Grade} {course5Credit}");
    ```

## Check your work

In this task, we will run the code and verify the output is correct.

1. In the .NET Editor, select **Run**.

1. Review your output and verify that the course names, grades, and credit hours are all correct:

    ```
    English 101 4 3
    Algebra 101 3 3
    Biology 101 3 4
    Computer Science I 3 4
    Psychology 101 4 3
    ```

    If your code displays different results, you will need to review your code to find your error and make updates. Run the code again to see if you have fixed the problem. Continue updating and running your code until your code produces the expected results.
