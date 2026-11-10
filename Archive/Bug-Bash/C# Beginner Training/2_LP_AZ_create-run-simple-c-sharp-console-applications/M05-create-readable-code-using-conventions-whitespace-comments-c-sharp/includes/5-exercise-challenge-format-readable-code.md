---
title: Exercise - Complete a challenge activity to improve code readability
durationInMinutes: 3
---
Code challenges throughout these modules will reinforce what you've learned and help you gain some confidence before continuing on.

## Code readability challenge

In this challenge, you'll use the techniques you learned in this module to improve the readability of a code sample. You are provided with a code sample that is poor poorly styled and commented. Your goal is to update the code using style guidelines for variable names, code comments, and whitespace to improve code readability.

## Code challenge - apply style guidelines to improve readability

1. Ensure that you have an empty Program.cs file open in Visual Studio Code.

    If necessary, open Visual Studio Code, and then complete the following steps to prepare a Program.cs file in the Editor:

    1. On the **File** menu, select **Open Folder**.

    1. Use the Open Folder dialog to navigate to, and then open, the **CsharpProjects** folder.

    1. In the Visual Studio Code EXPLORER panel, select **Program.cs**.

    1. On the Visual Studio Code **Selection** menu, select **Select All**, and then press the Delete key.

1. To create the initial code for this challenge, enter the following code:

    ```c#
    string str = "The quick brown fox jumps over the lazy dog.";
    // convert the message into a char array
    char[] charMessage = str.ToCharArray();
    // Reverse the chars
    Array.Reverse(charMessage);
    int x = 0;
    // count the o's
    foreach (char i in charMessage) { if (i == 'o') { x++; } }
    // convert it back to a string
    string new_message = new String(charMessage);
    // print it out
    Console.WriteLine(new_message);
    Console.WriteLine($"'o' appears {x} times.");
    ```

    > [!NOTE]
    > This code sample may include .NET Class Library methods that are unfamiliar to you. For example, you may not be familiar with the `ToCharArray()` method of the `String` class, or the `Reverse` method of the `Array` class. You do not need to fully understand the code sample in order to be successful in this challenge.

    > [!TIP]
    > The high-level purpose of this code is to reverse a string and count the number of times a particular character appears.

1. To improve readability, update the code using style guidelines.

    Use the techniques that you learned in this module to make improvements to the code and increase its readability.

Whether you get stuck and need to peek at the solution or you finish successfully, continue on to view a solution to this challenge.
