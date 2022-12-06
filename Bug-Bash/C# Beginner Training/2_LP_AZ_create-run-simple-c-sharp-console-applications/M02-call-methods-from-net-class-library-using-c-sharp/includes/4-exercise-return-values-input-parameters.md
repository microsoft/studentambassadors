---
title:   Exercise - Return values and input parameters of methods
durationInMinutes: 3
---
In the previous unit, we used the roll dice code to illustrate the two different methods: stateful (instance) and stateless (static) methods. However, that same code example can help us understand other critical ideas about calling methods like handling return values, accepting input parameters, and choosing an overloaded version of a method.

## Return values

Some methods are designed to complete their function, and end "quietly". In other words, they don't return values when they finish. They are referred to as **void methods**.

Other methods that are designed to return a value upon completion. The return value is typically the result of an operation. A return value is the primary way for a method to communicate back to the code that calls the method.

A method can be designed to return any data type, even another class. For example, the `Random.Next()` method returns an `int` value of the randomly generated number. We save the return value into a variable for use later in our code. We could have ignored the return value like so:

```c#
dice.Next(1, 7);
```

However, ignoring the return value would be pointless. The reason we're calling this method is so that we can retrieve the next random value from the Random object.

## Input parameters

Some methods are designed to work without any input parameters. These methods don't need any other input to complete their task. For example, the `Console.Clear()` method doesn't require any input parameters.

Other methods are designed to accept one or more input parameters. The input parameters can be used to configure how the method performs its work, or they might be operated on directly. We will be examining both of these cases below.

When calling methods that accept input parameters, separate each parameter with a `,` symbol.

In the following line of code, the two input parameters are used to configure the lower and upper boundaries for the `Next()` method as it generates a new random number.

```c#
int roll = dice.Next(1, 7);
```

And in the following line of code, the input parameter is what the `WriteLine()` operates on to write information to the console.

```c#
Console.WriteLine(roll);
```

Input parameters are defined using a data type. We can't pass values of a different data type as input parameters and expect the method to work. Instead, the C# compiler will catch a mistake and force a code modification before it compiles and runs it. Type checking is one way C# and .NET users check data types to prevent end-users from experiencing exceptions.

Methods use a **method signature** to define the number of input parameters required and the data type of each parameter.

## Overloaded methods

Many methods in the .NET Class Library have *overloaded* method signatures.

An **overloaded method** is defined with multiple method signatures. Overloaded methods provide different ways to call the method or provide different types of data.

In some cases, overloaded versions of a method are used to accept an input parameter using different data types. For example, the `Console.WriteLine()` method has 19 different overloaded versions. Most of those overloads allow the method to accept different types and then write the specified information to the console. Consider the following code:

```c#
int number = 7;
string text = "seven";

Console.WriteLine(number);
Console.WriteLine();
Console.WriteLine(text);

```

In this example, we're invoking three separate overloaded versions of the `WriteLine()` method.

- The first `WriteLine()` method uses a method signature that accepts an `int` parameter.
- The second `WriteLine()` method uses a method signature that accepts zero input parameters.
- The third `WriteLine()` method uses a method signature that accepts a `string` parameter.

In other cases, overloaded versions of a method accept a different number of input parameters. The alternative input parameters can be used to provide more control over desired result. For example, the `Random.Next()` method has three different overloaded versions. The three versions enable use to set various levels of constraint on the randomly generated number.

1. Ensure that you have an empty Program.cs file open in Visual Studio Code.

    If necessary, open Visual Studio Code, and then complete the following steps to prepare a Program.cs file in the Editor:

    1. On the **File** menu, select **Open Folder**.

    1. Use the Open Folder dialog to navigate to, and then open, the **CsharpProjects** folder.

    1. In the Visual Studio Code EXPLORER panel, select **Program.cs**.

    1. On the Visual Studio Code **Selection** menu, select **Select All**, and then press the Delete key.

1. To examine the overloaded versions of the `Random.Next()` method, enter the following code:

    ```c#
    Random dice = new Random();
    int roll1 = dice.Next();
    int roll2 = dice.Next(101);
    int roll3 = dice.Next(50, 101);
    
    Console.WriteLine($"First roll: {roll1}");
    Console.WriteLine($"Second roll: {roll2}");
    Console.WriteLine($"Third roll: {roll3}");
    
    ```

1. On the Visual Studio Code **File** menu, click **Save**.

1. In the EXPLORER panel, to open a Terminal at your TestProject folder location, right-click **TestProject**, and then select **Open in Integrated Terminal**.

    Ensure that folder path displayed in the command prompt points to the folder containing your Program.cs file.
  
1. At the Terminal command prompt, to run your code, type **dotnet run** and then press Enter.

    Notice that your result is similar to the following output:

    ```Output
    First roll: 342585470
    Second roll: 43
    Third roll: 89
    ```

    The numbers generated are random, so your results will be different. However, this example demonstrates the range of results that you might see.

1. Take a minute to examine the code.

    The first version of the `Next()` method doesn't set an upper and lower boundary, so the method will return values ranging from `0` to `2,147,483,647`, which is the maximum value an `int` can store.

    The second version of the `Next()` method specifies the maximum value as an upper boundary, so in this case, we can expect a random value between `0` and `100`.

    The third version of the `Next()` method specifies both the minimum and maximum values, so in this case, we can expect a random value between `50` and `100`.

1. Close the Terminal panel.

We've already covered several topics in this unit. Here's a quick list of what we've discussed:

- We've discussed how to use a method's return value (when the method provides a return value).
- We've discussed how a method can use input parameters that are defined as specific data types.
- We've discussed the overloaded versions of some methods that include different input parameters or parameter types.

### Use IntelliSense

Visual Studio Code includes *IntelliSense* features that are powered by a language service. In our case, the C# language service provides intelligent code completions based on language semantics and an analysis of our source code. In this section, we'll use IntelliSense to help us implement the `Random.Next()` method.

Since IntelliSense is exposed within the code editor, we can learn a lot about a method without leaving the coding environment. IntelliSense provides hints and brief reference information in a popup window under caret as you enter your code. When you are typing code, the IntelliSense popup window will change its contents depending on the context.

For example, as you enter the word `dice` slowly, IntelliSense will show all C# keywords, identifiers (or rather, variable names in the code), and classes in the .NET Class Library that match the letters being entered. Autocomplete features of the code editor can be used to finish typing the word that is the top match in the IntelliSense popup. Let's try it out.

1. Ensure that you have your Program.cs file open in Visual Studio Code.

    Your app should contain the following code:

    ```c#
    Random dice = new Random();
    int roll1 = dice.Next();
    int roll2 = dice.Next(101);
    int roll3 = dice.Next(50, 101);
    
    Console.WriteLine($"First roll: {roll1}");
    Console.WriteLine($"Second roll: {roll2}");
    Console.WriteLine($"Third roll: {roll3}");
    
    ```

1. At the bottom of your code file, to experiment with IntelliSense, slowly enter the letters `d`, `i` then `c`.

1. Notice the IntelliSense popup window that appears when you begin typing

    When IntelliSense pops up, a list of suggestions should appear. By the time you have entered `dic`, the identifier `dice` should be at the top of the list.

1. Press the Tab key on the keyboard.

    Notice that the entire word `dice` is completed in the editor. You can use the up and down arrow keys to change the selection before pressing the Tab key.

    > [!NOTE]
    > If the IntelliSense window disappears, it can be selected by using the `backspace` key on the keyboard, then re-enter the last symbol to re-open IntelliSense.

1. To specify the member access operator, enter a `.` character.

    Notice that the IntelliSense popup reappears when you enter `.` and shows an unfiltered list of all the methods (and other members of the class) that are available.

1. Enter **N**

    The list will be filtered, and the word `Next` should be the top selection.

1. To autocomplete the entire word, press the Tab key.

1. To specify the method invocation operator, enter **(**

    The method invocation operator is the set of parentheses located to the right of the method name. This portion of the method signature is where we specify the input parameters for the method. The method invocation operator is required when calling the method.

    Notice that the closing parenthesis is automatically added.

1. Take a minute to examine the areas that appear in the IntelliSense popup.

    If you look closely, you can see that the popup window includes three sections.

1. On the right side, you should see `int Random.Next()` on top and `Returns a non-negative random integer.` below.

    The `int` is the return type. In other words, when this version of the method is executed, it will return a value of type `int`.

1. On the left of the IntelliSense popup, it displays `1/3`.

    The `1/3` indicates that you're looking at the first of three method signatures for the `Next()` method. Notice that this version of the method signature enables the method to work with no input parameters.

    Notice that there's also a tiny arrow above and below the `1/3`.

1. To examine the second overloaded version of the method, select the keyboard's down arrow key.

    Notice that you can use the up and down arrow keys to navigate between the various overloaded versions. When you do, you'll see the `1/3`, `2/3`, and `3/3` appear on the left side of IntelliSense, and helpful explanations on the right.

1. Take a minute to examine each of the overloaded versions for the `Random.Next()` method.

    The second overloaded version of the method `2/3` informs that the `Next()` method can accept an input parameter `int maxValue`. The description tells us that `maxValue` is the exclusive upper bound for the number that we want the `Next()` method to generate. Exclusive indicates that the return number will be less than `maxValue`.

    The third version of the method `3/3` informs you that the `Next()` method can accept both `int minValue` and `int maxValue` as input parameters.  The `minValue` is lower bound for the number that we want the `Next()` method to generate. Since the lower bound is not exclusive, the return value can be equal to `minValue`.

    In this case, IntelliSense provides all of the information that we need to select the appropriate overload, including a detailed explanation of `maxValue` and `minValue`. However, you may encounter situations where you need to consult the method's documentation.

### Use docs.microsoft.com for information about overloaded methods

The second way to learn about overloaded versions of the methods is to consult the documentation for the method. The documentation will also help you to understand exactly what each input parameter is intended for.

1. To begin, open your preferred Web browser and search engine.

1. Perform a search for **C# Random.Next()**

    Your search should include the class name and method name. You may also want to include the term `C#` to make sure not to accidentally get results for other programming languages.

1. Select the top search result with a URL that begins with `https://learn.microsoft.com`.

    One of the top search results should lead to a URL that begins with `https://learn.microsoft.com`. In our case, the link's title should appear as `Random.Next Method`.

    Here's the link in case you have a problem finding it using a search engine:

    [Random.Next Method](https://learn.microsoft.com/dotnet/api/system.random.next)

1. Open the link for **C# Random.Next()**.

1. Quickly scan through the documentation.

    Scroll down through the page contents to see the various code samples. Notice that you can run the samples in the browser window.

    The learn.microsoft.com documentation follows a standard format for each class and method in the .NET Class Library.

1. Near the top of the web page, locate the section labeled **Overloads**.

    Notice that there are three overloaded versions of the method listed. Each overloaded version that's listed includes a hyperlink to a location further down on the page.

1. To navigate "on-page" to a description of the second overloaded version, select **Next(Int32)**.

    Documentation for each version of the method includes:

    - Brief description of the method's functionality
    - Method's definition
    - Input parameters that the method accepts
    - Return values
    - Exceptions that can be raised
    - Examples of the method in use
    - Other remarks about the method

1. Take a minute to review the **Parameters** section.

    In the *Parameters* section, we read that the `maxValue` input parameter is the "exclusive upper bound of the random number to be generated." An *exclusive upper bound* means that if we want numbers no larger than `10`, we must pass in the value `11`.

    We can also read in the next line: "`maxValue` must be greater than or equal to 0." What happens if we ignore this statement? We can see in the *Exceptions* section that the method will return an `ArgumentOutOfRangeException` when `maxValue` is less than 0.

    > [!NOTE]
    > The content at learn.microsoft.com is the "source of truth" for the .NET Class Library. It's important to take the time to read the documentation to understand how a given method will work.

## Recap

- Methods may accept no parameters or multiple parameters, depending on how they were designed and implemented. When passing in multiple input parameters, separate them with a `,` symbol.
- Methods may return a value when they complete their task, or they may return nothing (void).
- Overloaded methods support several implementations of the method, each with a unique method signature (the number of input parameters and the data type of each input parameter).
- IntelliSense can help write code more quickly. It provides a quick reference to methods, their return values, their overloaded versions, and the types of their input parameters.
- docs.microsoft.com is the "source of truth" when you want to learn how methods in the .NET Class Library work.

## quiz title: Check your knowledge

## Multiple Choice

What is a return value?
(x) It is a value type returned by a method.{{Correct! This is the correct definition of a return value.}}
( ) The money received returning a library book. {{Incorrect. A return value in this context has nothing to do with library books.}}
( ) A string value. {{Incorrect. A return value could be a string, but it could also be an int32, a float, a custom type, or something else.}}

## Multiple Choice

What are input parameters?
(x) Value types (or variables) passed into a method. {{Correct! This is the correct definition of an input parameter.}}
( ) Values returned by a method. {{Incorrect. Input values are passed into a method, not returned from a method.}}
( ) Telemetry signals {{Incorrect. Although you can pass any sort of value(s) into a method, by definition, parameter values are not telemetry signals.}}

## Multiple Choice

What is an overloaded method?
( ) A method that ate too much. {{Incorrect. Methods do not eat.}}
( ) A method with more than five parameters. {{Incorrect. An overloaded method can have any number of parameters.}}
(x) It is a method that supports several implementations of the method, each with a unique method signature. {{Correct! This is the correct definition of an overloaded method.}}

## Multiple Choice

How does IntelliSense help you?
(x) IntelliSense can help you write code more quickly. {{Correct! IntelliSense can catch misspelling, incorrect usage, and suggest corrections. These things speed up the coding process.}}
( ) It helps you refactoring your code. {{Incorrect. While it can help you with your coding, it is not primarily refactoring tool.}}
( ) It can change the \"theme\" of your IDE. {{Incorrect. It is not used for this purpose.}}
