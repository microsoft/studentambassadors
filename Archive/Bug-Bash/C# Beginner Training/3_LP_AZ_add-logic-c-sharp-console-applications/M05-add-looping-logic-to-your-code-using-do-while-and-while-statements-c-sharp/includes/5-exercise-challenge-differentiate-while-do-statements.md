Code challenges throughout these modules will reinforce what you've learned and help you gain some confidence before continuing on.

## Examine the difference between do and while statement iterations  

As we have seen, C# supports four types of iteration statements: `for`, `foreach`, `do-while`, and `while`. Microsoft's language reference documentation describes these statements as follows:

- The `for` statement: executes its body while a specified Boolean expression evaluates to true.
- The `foreach` statement: enumerates the elements of a collection and executes its body for each element of the collection.
- The `do-while` statement: conditionally executes its body one or more times.
- The `while` statement: conditionally executes its body zero or more times.

The `for` and `foreach` iterations seem to be clearly differentiated from each other and from the `do-while` and `while` iterations. The definitions for the `do-while` and `while` statements, however, appear to be quite similar. Knowing when to choose between a `do-while` and a `while` seems more arbitrary, and can even be a bit confusing. Some challenge projects may help to make the differences clear.

In this challenge, we'll set the conditions for some coding projects. Each project will require you to implement an iteration code block using either a `do-while` or a `while` statement. You'll need to evaluate the specified conditions in order to choose between the `do-while` and `while` statements. You can switch after you start if your first choice isn't working out as well as you had hoped.

> [!NOTE]
> The conditions for your coding project can be used to help you select between the `do-while` and `while` statements. What you know, or don't know, about the Boolean expression that will be evaluated can sometimes help you to select between the `do-while` and `while` statements. In this challenge exercise, the project conditions include information that will be used to construct the Boolean expression.

## Code project 1 - write code that validates integer input

Here are the conditions that your first coding project must implement:

- Your solution must include either a `do-while` or `while` iteration.
- Before the iteration block: your solution must use a `Console.WriteLine()` statement to prompt the user for an integer value between 5 and 10.
- Inside the iteration block:

  - Your solution must use a `Console.ReadLine()` statement to obtain input from the user.
  - Your solution must ensure that the input is a valid representation of an integer.
  - If the integer value is not between 5 and 10, your code must use a `Console.WriteLine()` statement to prompt the user for an integer value between 5 and 10.
  - Your solution must ensure that the integer value is between 5 and 10 before exiting the iteration.

- Below (after) the iteration code block: your solution must use a `Console.WriteLine()` statement to inform the user that their input value has been accepted.

1. Ensure that you have an empty Program.cs file open in Visual Studio Code.

    If necessary, open Visual Studio Code, and then complete the following steps to prepare a Program.cs file in the Editor:

    1. On the **File** menu, select **Open Folder**.

    1. Use the Open Folder dialog to navigate to, and then open, the **CsharpProjects** folder.

    1. In the Visual Studio Code EXPLORER panel, select **Program.cs**.

    1. On the Visual Studio Code **Selection** menu, select **Select All**, and then press the Delete key.

1. Write the code that implements each condition.

1. Run your application and verify that your code validates user input based on the specified requirements.

    For example, when you run your application, it should reject input values such as "two" and "2", but it should accept an input value of "7".

    The example described above, the console output should look similar to the following:

    ```Output
    Enter an integer value between 5 and 10
    two
    Sorry, you entered an invalid number, please try again
    2
    You entered 2. Please enter a number between 5 and 10.
    7
    Your input value (7) has been accepted.
    ```

## Code project 2 - write code that validates string input

Here are the conditions that your second coding project must implement:

- Your solution must include either a `do-while` or `while` iteration.
- Before the iteration block: your solution must use a `Console.WriteLine()` statement to prompt the user for one of three role names: Administrator, Manager, or User.
- Inside the iteration block:

  - Your solution must use a `Console.ReadLine()` statement to obtain input from the user.
  - Your solution must ensure that the value entered matches one of the three role options.
  - Your solution should use the `Trim()` method on the input value to ignore leading and training space characters.
  - Your solution should use the `ToLower()` method on the input value to ignore case.
  - If the value entered is not a match for one of the role options, your code must use a `Console.WriteLine()` statement to prompt the user for a valid entry.

- Below (after) the iteration code block: Your solution must use a `Console.WriteLine()` statement to inform the user that their input value has been accepted.

1. Comment out all of the code in the Visual Studio Code Editor panel

    1. Select all of the code lines in the code editor
    1. On the **Edit** menu, select **Toggle Block Comment**.

1. Write the code that implements each condition.

1. Run your application and verify that your code validates user input based on the specified requirements.

    For example, when you run your application, it should reject an input value such as "Admin", but it should accept an input value of "  administrator ".

    The console output for this example should look similar to the following:

    ```Output
    Enter your role name (Administrator, Manager, or User)
    Admin
    The role name that you entered, "Admin" is not valid. Enter your role name (Administrator, Manager, or User)
       Administrator
    Your input value (Administrator) has been accepted.
    ```

## Code project 3 - Write code in the code editor to implement code that achieves the project conditions

Here are the conditions that your third coding project must implement:

- your solution must use the following string array to represent the input to your coding logic:

    ```c#
    string[] myStrings = new string[2] { "I like pizza. I like roast chicken. I like salad", "I like all three of the menu choices" };
    ```

- Your solution must declare an integer variable named `periodLocation` that can be used to hold the location of the period character within a string.
- Your solution must include an outer `foreach` or `for` loop that can be used to process each string element in the array. The string variable that you will process inside the loops should be named `myString`.
- In the outer loop, your solution must use the `IndexOf()` method of the `String` class to get the location of the first period character in the `myString` variable. The method call should be similar to: `myString.IndexOf(".")`. If there is no period character in the string, a value of -1 will be returned.  
- Your solution must include an inner `do-while` or `while` loop that can be used to process the `myString` variable.
- In the inner loop, your solution must extract and display (write to the console) each sentence that is contained in each of the strings that are processed.
- In the inner loop, your solution must not display the period character.
- In the inner loop, your solution must use the `Remove()`, `Substring()`, and `TrimStart()` methods to process the string information.

1. Comment out all of the code in the Visual Studio Code Editor panel

    1. Select all of the code lines in the code editor
    1. On the **Edit** menu, select **Toggle Block Comment**.

1. Write the code that implements each condition.

1. Run your application and verify that your output meets the requirements.

    If your code logic works correctly, your output should look similar to the following:

    ```Output
    I like pizza
    I like roast chicken
    I like salad
    I like all three of the menu choices
    ```

Whether you get stuck and need to peek at the solution or you finish successfully, continue on to view the solution projects for this challenge.
