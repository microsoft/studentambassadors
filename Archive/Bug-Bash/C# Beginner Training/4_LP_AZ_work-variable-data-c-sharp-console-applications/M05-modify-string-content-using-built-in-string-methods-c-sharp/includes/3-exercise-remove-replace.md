---
title: Exercise - Use the Remove() and Replace() methods
durationInMinutes: 8
---

In the previous unit, we learned how to locate the position of a character or string within another string. We used the position to extract a sub string.

Sometimes, we'll need to modify the contents of the string, removing or replacing characters. While we could do this with the tools we already know, it requires a bit of temporarily storing and stitching strings back together. Fortunately, the `string` data type has additional built-in methods for these specialized scenarios.

## Exercise - Use the Remove() and Replace() methods

In this exercise, we'll remove characters from a string using the `Remove()` method and replace characters using the `Replace()` method.

### Step 1 - Write code to remove characters in specific locations from a string

You would typically use `Remove()` when there's a standard and consistent position of the characters you want to remove from the string.

Sometimes, data stored in older files is fixed length, where character positions are allocated for certain fields of information. In this first step of our exercise, we have such a fictitious record of information. The first five digits represent a customer identification number. The next 20 digits contain a customer's name. The next six positions represent the customer's latest invoice amount, and the last three positions represent the number of items ordered on that invoice.

Perhaps we need to remove the customer's name to format the data so that it can be sent to a separate process. Since we know the exact position and length of the user's name, we can easily remove it using the `Remove()` method.

1. Delete or use the line comment operator `//` to comment out all of the code from the previous exercises.

1.	Update your code in the Visual Studio Code Editor as follows:

    ```c#
    string data = "12345John Smith          5000  3  ";
    string updatedData = data.Remove(5, 20);
    Console.WriteLine(updatedData);
    ```

1. On the Visual Studio Code **File** menu, select **Save**.

    The Program.cs file must be saved before building or running the code.

1. In the EXPLORER panel, to open a Terminal at your TestProject folder location, right-click **TestProject**, and then select **Open in Integrated Terminal**.

    A Terminal panel should open, and should include a command prompt showing that the Terminal is open to your TestProject folder location.

1. At the Terminal command prompt, to run your code, type **dotnet run** and then press Enter.

    > [!NOTE]
    > If you see a message saying "Couldn't find a project to run", ensure that the Terminal command prompt displays the expected TestProject folder location. For example: `C:\Users\someuser\Desktop\csharpprojects\TestProject>`

    You should see the following output:

    ```Output
    123455000  3  
    ```

The `Remove()` method works similarly to the `Substring()` method. You supply a starting position and the length to remove those characters from the string.

### Step 2 - Write code to remove characters no matter where they appear in a string

You would use the `Replace()` method when you must replace one or more characters with a different character (or no character). The `Replace()` method is different from the other methods we've used so far inasmuch as it will replace every instance of the given characters, not just the first or last instance.

1.	Update your code in the Visual Studio Code Editor as follows:

    ```c#
    string message = "This--is--ex-amp-le--da-ta";
    message = message.Replace("--", " ");
    message = message.Replace("-", "");
    Console.WriteLine(message);
    ```

1. Save your code file, and then use Visual Studio Code to run your code. You should see the following output:

    ```Output
    This is example data
    ```

Here we used the `Replace()` method twice. The first time we replaced the string `--` with an empty space. The second time we replaced the string `-` with an empty string, which completely removes the character from the string.

## Recap

Here's the most important things to remember from this unit:

- The `Remove()` method works like the `Substring()` method, except that it deletes the specified characters in the string.
- The `Replace()` method swaps all instances of a string with a new string.

## Check your knowledge

## Multiple Choice

If the code `message = message.Replace("B", "D");` is run, where `string message = "Big Dog";`, what is the new value of `message`?
( ) `"Big Dog"` {{That's incorrect. `"B"` is replaced by `"D"`.}}
( ) `"Big Bog"` {{That's incorrect. `"B"` is replaced by `"D"`.}}
(x) `"Dig Dog"` {{That's correct. `"B"` is replaced by `"D"`.}}
