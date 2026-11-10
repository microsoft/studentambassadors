Code challenges throughout these modules will reinforce what you've learned and help you gain some confidence before continuing on.

## FizzBuzz challenge

FizzBuzz is a popular coding challenge and interview question. It exercises your understanding of the `for` statement, the `if` statement, the `%` remainder operator, and your command of basic logic.

## Code challenge - implement the FizzBuzz challenge rules

Here are the FizzBuzz rules that you need to implement in your code project:

- Output values from 1 to 100, one number per line, inside the code block of an iteration statement.
- When the current value is divisible by 3, print the term `Fizz` next to the number.
- When the current value is divisible by 5, print the term `Buzz` next to the number.
- When the current value is divisible by **both** 3 and 5, print the term `FizzBuzz` next to the number.

1. Ensure that you have an empty Program.cs file open in Visual Studio Code.

    If necessary, open Visual Studio Code, and then complete the following steps to prepare a Program.cs file in the Editor:

    1. On the **File** menu, select **Open Folder**.

    1. Use the Open Folder dialog to navigate to, and then open, the **CsharpProjects** folder.

    1. In the Visual Studio Code EXPLORER panel, select **Program.cs**.

    1. On the Visual Studio Code **Selection** menu, select **Select All**, and then press the Delete key.

1. Write the code that implements each rule.

    > [!IMPORTANT]
    > You will need to understand how to use the `%` remainder operator to determine if a number is divisible by another number evenly. We covered this in the module "Perform basic operations on numbers in C#".

1. Run your application and verify that your output meets the requirements.

    No matter how you have nested you iteration and conditional statements, your code should produce the following output.

    ```Output
    1
    2
    3 - Fizz
    4
    5 - Buzz
    6 - Fizz
    7
    8
    9 - Fizz
    10 - Buzz
    11
    12 - Fizz
    13
    14
    15 - FizzBuzz
    16
    17
    18 - Fizz
    19
    20 - Buzz
    21 - Fizz
    22
    .
    .
    .
    ```

    > [!NOTE]
    > We only show the first 22 values, but your output should continue to 100. As you can see, the number `15` is divisible by both 3 and 5, so we print `FizzBuzz` next to that number.

Whether you get stuck and need to peek at the solution or you finish successfully, continue on to view a solution to this challenge.
