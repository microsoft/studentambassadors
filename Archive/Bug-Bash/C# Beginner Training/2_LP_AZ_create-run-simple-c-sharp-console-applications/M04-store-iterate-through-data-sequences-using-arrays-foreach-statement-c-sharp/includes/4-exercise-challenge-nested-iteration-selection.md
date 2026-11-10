---
title:  Exercise - Complete a challenge activity for nested iteration and selection statements
durationInMinutes: 3
---
Code challenges throughout these modules will reinforce what you've learned and help you gain some confidence before continuing on.

## Fraudulent order challenge

Earlier in this module, we set out to write code that would store Order IDs belonging to potentially fraudulent orders. Our goal is to find fraudulent orders as early as possible and flag them for deeper analysis.

## Code challenge - report the Order IDs that need further investigation

Our team has found a pattern. Orders that start with the letter "B" encounter fraud at a rate 25 times greater than the normal rate. We'll write new code that outputs the Order ID of new orders where the Order ID starts with the letter "B". This will be used by our fraud team to investigate further.

Use the following steps to complete this challenge.

1. Ensure that you have an empty Program.cs file open in Visual Studio Code.

    If necessary, open Visual Studio Code, and then complete the following steps to prepare a Program.cs file in the Editor:

    1. On the **File** menu, select **Open Folder**.

    1. Use the Open Folder dialog to navigate to, and then open, the **CsharpProjects** folder.

    1. In the Visual Studio Code EXPLORER panel, select **Program.cs**.

    1. On the Visual Studio Code **Selection** menu, select **Select All**, and then press the Delete key.

1. Declare an array and initialize it to contain the following elements:

    ```Output
    B123
    C234
    A345
    C15
    B177
    G3003
    C235
    B179
    ```

    These values represent the fraudulent Order ID data that your application will use.

1. Create a `foreach` statement to iterate through each element of your array.

1. Report the Order IDs that start with the letter "B".

    You will need to evaluate each element of the array. Report the potentially fraudulent Order IDs by detecting the orders that start with the letter "B". To determine whether or not an element starts with the letter "B", use the `String.StartsWith()` method. Here's a simple example of how to use the `String.StartsWith()` method that you can adapt for your code:

    ```c#
    string name = "Bob";
    if (name.StartsWith("B"))
    {
        Console.WriteLine("The name starts with 'B'!");
    }
    ```

    Your output should match the following:

    ```Output
    B123
    B177
    B179
    ```

> [!TIP]
> Here's a hint: As you loop through each element in your array, you'll need an `if` statement. The `if` statement will need to use a method on the string class to determine if a string starts with a specific letter. If you're not sure how to use an `if` statement, please see the module "Add decision logic to your code using the if-elseif-else statement in C#".

Whether you get stuck and need to peek at the solution or you finish successfully, continue on to view a solution to this challenge.
