"Decision logic" and "branching logic" are terms programmers use to describe the change in execution path based on the evaluation of some expression. For example, we may write code that evaluates user input. If the value the user inputs is equal to the string value "a", we execute one code block. If the value the user inputs is equal to the string value "b", we execute a different code block. In this example, we're changing the execution path of our application based on user input. This change in execution path is what is meant by the terms "branching" and "decision".

But before we work with the logic statements, let's start by talking about how to evaluate an expression.

## What is an expression?

An expression is any combination of values (literal or variable), operators, and methods that return a single value. A statement is a complete instruction in C#, and statements are comprised of one or more expressions. For example, the following `if` *statement* contains a single *expression* that returns a single value:

```c#
if (myName == "Chris")
```

There are many different categories of expressions, but when working with decision statements, we're interested in Boolean expressions. In a Boolean expression, the runtime evaluates the values, operators, and methods to return a single true or false value.

Boolean expressions are important because decision statements, which we'll learn about next, use these expressions to decide which block of code to execute.

There are many different operators we can use within a Boolean expression. The operator that we choose will depend on what we want to express in our code.

## Evaluating equality and inequality

Many times, you'll want to check to see if two values are equal or not. You use the equality operator `==` between two values to evaluate equality. If the two values on either side of the equality operator are equivalent, then the expression will return `true`. Otherwise, it will return `false`.

Other times, you may want to check to see if two values aren't equal. You use the inequality operator `!=` between two values evaluate equality.

You may wonder why you need both equality and inequality operators. The reason will become clearer as you learn how to create branching statements and begin to write real world code. Two operators that perform opposite tasks allow you to be more expressive and compact.

Okay, now let's prepare our coding environment and begin our examination of code samples that evaluate expressions.

### Prepare your coding environment

This module includes hands-on activities that guide you through the process of building and running demonstration code. We encourage you to complete these activities using Visual Studio Code as your development environment. Using Visual Studio Code for these activities will help you to become more comfortable writing and running code in a developer environment that's used by professionals worldwide.

1. Open Visual Studio Code.

    You can use the Windows Start menu (or equivalent resource for another OS) to open Visual Studio Code.

1. On the Visual Studio Code **File** menu, select **Open Folder**.

1. In the **Open Folder** dialog, navigate to the Windows Desktop folder.

    If you have different folder location where you keep code projects, you can use that folder location instead. For this training, the important thing is to have a location that’s easy locate and remember.

1. In the **Open Folder** dialog, select **Select Folder**.

    If you see a security dialog asking if you trust the authors, select **Yes**.

1. On the Visual Studio Code **Terminal** menu, select **New Terminal**.

    Notice that a command prompt in the Terminal panel displays the folder path for the current folder. For example:  

    ```dos
    C:\Users\someuser\Desktop>
    ```

    > [!NOTE]
    > If you are working on your own PC rather than in a sandbox or hosted environment and you have completed other Microsoft Learn modules in this C# series, you may have already created a project folder for code samples. If that's the case, you can skip over the next step, which is used to create a console app in the TestProject folder.

1. At the Terminal command prompt, to create a new console application in a specified folder, type **dotnet new console -o ./CsharpProjects/TestProject** and then press Enter.

    This .NET CLI command uses a .NET program template to create a new C# console application project in the specified folder location. The command creates the CsharpProjects and TestProject folders for us, and uses TestProject as the name of our `.csproj` file.

1. In the EXPLORER panel, expand the **CsharpProjects** folder.

    You should see the TestProject folder and two files, a C# program file named Program.cs and a C# project file named TestProject.csproj.

1. In the EXPLORER panel, to view your code file in the Editor panel, select **Program.cs**.

1. Delete the existing code lines.

    You'll be using this C# console project to create, build, and run code samples during this module.

1. Close the Terminal panel.

### Step 1 - Use the equality operator

1. Ensure that you have Visual Studio Code open and Program.cs displayed in the Editor panel.

    > [!NOTE]
    > Program.cs should be empty. If if isn't, select and delete all code lines.

1. Type the following code into the Visual Studio Code Editor.

    ```c#
    Console.WriteLine("a" == "a");
    Console.WriteLine("a" == "A");
    Console.WriteLine(1 == 2);
    
    string myValue = "a";
    Console.WriteLine(myValue == "a");
    ```

1. On the Visual Studio Code **File** menu, select **Save**.

    The Program.cs file must be saved before building or running the code.

1. In the EXPLORER panel, to open a Terminal at your TestProject folder location, right-click **TestProject**, and then select **Open in Integrated Terminal**.

    A Terminal panel should open, and should include a command prompt showing that the Terminal is open to your TestProject folder location.

1. At the Terminal command prompt, to run your code, type **dotnet run** and then press Enter.

    > [!NOTE]
    > If you see a message saying "Couldn't find a project to run", ensure that the Terminal command prompt displays the expected TestProject folder location. For example: `C:\Users\someuser\Desktop\csharpprojects\TestProject>`

    You should see the following output.

    ```c#
    True
    False
    False
    True
    ```

### Step 2 - Improve the check for string equality using the string's built-in helper methods

You may be surprised that the line `Console.WriteLine("a" == "A");` outputs `false`. When comparing strings, case matters.

Also, consider this line of code:

```c#
Console.WriteLine("a" == "a ");
```

Here we add a blank space at the end of the string. This expression will also output `false`.

In some cases, having a space character before or after the text might be perfectly acceptable. However, if you need to accept a match that isn't exact, you can "massage" the data first. "Massaging" the data means that you perform some cleanup before you perform a comparison for equality. For example, consider the case when you are collecting user input. Perhaps you provide the user with a prompt in order to determine if they want to continue, such as `Do you want to continue (Y/N)?`. The user could enter `y` or `Y`, or even ` y` or ` Y`. Chances are you don't want to consider a `y`, ` y`, or ` Y` response to mean that they don't want to continue even though those strings are not equivalent to `Y`.

Before you check two string values for equality, especially when one or both values that were input by a user, you should:

- Make sure both strings are all upper-case or all lower-case using the `ToUpper()` or `ToLower()` helper method on any string value.
- Remove any leading or trailing blank spaces using the `Trim()` helper method on any string value.

Let's improve the previous equality check by chaining these two helper methods on both values, as shown in the following code listing:

1. Update your code in the Visual Studio Code Editor as follows:

    ```c#
    string value1 = " a";
    string value2 = "A ";
    Console.WriteLine(value1.Trim().ToLower() == value2.Trim().ToLower());
    ```

1. Save your code file, and then use Visual Studio Code to run your code.

1. Notice that when you run the code this time, the output is `true`.

### Step 3 - Use the inequality operator

1. Use the line comment operator `//` to comment out all of the code from the previous step.

1. Type the following code into the Visual Studio Code Editor.

    ```c#
    Console.WriteLine("a" != "a");
    Console.WriteLine("a" != "A");
    Console.WriteLine(1 != 2);
    
    string myValue = "a";
    Console.WriteLine(myValue != "a");
    ````

1. Save your code file, and then use Visual Studio Code to run your code.

    You should see the following output.

    ```c#
    False
    True
    True
    False
    ```

As we would expect, the result when using the inequality operator is the opposite of what we saw when using the equality operator. That means that our code will branch in the opposite manner as well, which can be exactly what we want.

## Evaluating comparisons

When working with numeric data types, you may want to determine if a value is larger than, or smaller than, another value. Use the following operators to perform these types of comparisons.

- Greater than `>`
- Less than `<`
- Greater than or equal to `>=`
- Less than or equal to `<=`

Naturally, the `==` and `!=` operators that we used to compare string values above will also work when comparing numeric data types.

### Step 4 - Use the Comparison operators

1. Use the line comment operator `//` to comment out all of the code from the previous step.

1. Type the following code into the Visual Studio Code Editor.

    ```c#
    Console.WriteLine(1 > 2);
    Console.WriteLine(1 < 2);
    Console.WriteLine(1 >= 1);
    Console.WriteLine(1 <= 1);
    ```

1. Save your code file, and then use Visual Studio Code to build and run your code.

    You should see the following output.

    ```c#
    False
    True
    True
    True
    ```

## Methods that return a Boolean value

Some methods return a Boolean value. You can think of these types of methods as queries. In the following exercise, we'll use a built-in method of the String class to determine whether or not a larger string contains a specific word or phrase that may be interesting to us.

> [!NOTE]
> Some data types have methods that perform helpful utility tasks. The String data type has many of these. Several return a Boolean value including `Contains()`, `StartsWith()`, and `EndsWith()`. You can learn more about them in the Microsoft Learn module "Manipulate alphanumeric data using String class methods in C#".

### Step 5 - Use a method invocation expression

1. Use the line comment operator `//` to comment out all of the code from the previous step.

1. Type the following code into the Visual Studio Code Editor.

    ```c#
    string pangram = "The quick brown fox jumps over the lazy dog.";
    Console.WriteLine(pangram.Contains("fox"));
    Console.WriteLine(pangram.Contains("cow"));
    ```

1. Save your code file, and then use Visual Studio Code to build and run your code.

    You should see the following output.

    ```c#
    True
    False
    ```

## What is logical negation?

The term "Logical Negation" refers to the `!` operator. Some people call this operator the "not operator". When you place the `!` operator before a conditional expression (or any code that's evaluated to either `true` or `false`), it forces your code to ensure that the expression is false.

Here is an example that may help you to see the connection between these ideas. The following two lines of code produce the same result. The second line is more compact.

```c#
// These two lines of code will create the same output

Console.WriteLine(pangram.Contains("fox") == false);
Console.WriteLine(!pangram.Contains("fox"));
```

### Step 6 - Use the Logical Negation operator

1. Use the line comment operator `//` to comment out all of the code from the previous step.

1. Type the following code into the Visual Studio Code Editor.

    ```c#
    string pangram = "The quick brown fox jumps over the lazy dog.";
    Console.WriteLine(!pangram.Contains("fox"));
    Console.WriteLine(!pangram.Contains("cow"));
    ```

1. Save your code file, and then use Visual Studio Code to build and run your code.

    You should see the following output.

    ```c#
    False
    True
    ```

## Recap

Here's the main takeaways you learned about evaluating Boolean expressions so far:

- There are many different kinds of expressions that evaluate to either `true` or `false`.
- Evaluate equality using the `==` operator.
- Evaluating equality of strings requires you consider the possibility that the strings have different case and leading or trailing spaces. Depending on your situation, use the `ToLower()` or `ToUpper()` helper methods, and the `Trim()` helper method to improve the likelihood that two strings are equal.
- Evaluate inequality using the `!=` operator.
- Evaluate greater than, less than and similar operations using comparison operators like `>`, `<`, `>=`, and `<=`.
- If a method returns a bool, it can be used as a Boolean expression.
- Use the logical negation operator `!` to evaluate the opposite of a given expression.

## quiz title: Check your knowledge

## Multiple Choice

Which of the following is a list of valid comparison operators?
( ) `==`, `~=`, `>`, `<`, `>=`, and `<=`. {{That's incorrect. `~=` is not a valid comparison operator.}}
( ) `==`, `<>`, `>`, `<`, `>=`, and `<=`. {{That's incorrect. `<>` is not a valid comparison operator.}}
(x) `==`, `!=`, `>`, `<`, `>=`, and `<=`. {{That's correct. `==`, `!=`, `>`, `<`, `>=`, and `<=` are all valid comparison operators.}}

## Multiple Choice

Which of the following code lines uses logical negation? 
( ) `Console.WriteLine(myValue != true);`. {{Incorrect. Evaluating that value isn't `true` isn't logical negation.}}
(x) `Console.WriteLine(!myValue);`. {{Correct! Adding the `!` operator before a conditional expression is the correct way to implement logical negation.}}
( ) `Console.WriteLine(myValue == false);`. {{Incorrect. Evaluating for `false` isn't logical negation.}}

## Multiple Choice

Your code contains two string variables named `myValue1` and `myValue2`. The user enters the following two values for these variables: "Y " and " y". Which of the following expressions will return `false`? 
( ) `(myValue1 != myValue2)`. {{Incorrect. This expression returns `true` because the two values are not equivalent.}}
(x) `(myValue1.Trim().ToLower() != myValue2.Trim().ToLower())`. {{Correct! This expression returns `false` since the two values are equal and we are using the inequality operator.}}
( ) `(myValue1.Trim().ToLower() == myValue2.Trim().ToLower())`. {{Incorrect. This expression returns `true` because the two values are equal and we are using the equality operator.}}
