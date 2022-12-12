---
title: Exercise - Examine the TryParse() method
durationInMinutes: 12
---

When working with data, you'll likely need to convert string data into a numeric data type. As you learned in the previous unit, because the string data type can hold a non-numeric value, it's possible that performing a conversion from a `string` into a numeric data type will cause a runtime error.

For example, the following code:

```c#
string name = "Bob";
Console.WriteLine(int.Parse(name));
```

causes the following exception:

```Output
System.FormatException: 'Input string was not in a correct format.'
```

To avoid a format exception, use the TryParse() method on the target data type.

## Use TryParse()

The TryParse() method does several things simultaneously:

- It attempts to parse a string into the given numeric data type.
- If successful, it will store the converted value in an **out parameter**.
- It returns a bool to indicate whether the action succeeded or failed.

We can use the bool to take action on the value (like performing some calculation), or display a message if the parse operation was unsuccessful.

> [!NOTE]
> In this exercise, we're using the `int` data type, but a similar `TryParse()` method is available on all numeric data types.

### What is an out parameter?

Methods can return a value or return "void", meaning they return no value. Methods can also return values through `out` parameters, which are defined just like an input parameter, but include the `out` keyword.

When calling a method with an `out` parameter, you must also use the keyword `out` before the variable, which will hold the value. So, you have to define a variable before calling the method that will be used to store an out parameter value. You can then use the value contained in the out parameter throughout the rest of your code.

### Step 1 - TryParse() a string into an int

1. Delete or use the line comment operator `//` to comment out all of the code from the previous exercises.

1. Update your code in the Visual Studio Code Editor as follows:

    ```c#
    string value = "102";
    int result = 0;
    if (int.TryParse(value, out result))
    {
        Console.WriteLine($"Measurement: {result}");
    }
    else
    {
        Console.WriteLine("Unable to report the measurement.");
    }
    ```

Let's focus on this line:

```
if (int.TryParse(value, out result))
```

The `int.TryParse()` method will return `true` if it successfully converted our `string` variable `value` into an `int`; otherwise, it will return `false`. So, surround the statement in an `if` statement, and then perform the decision logic, accordingly.

Note that the converted value will be stored in the `int` variable `result`. The `int` variable `result` is declared and initialized before this line of code, so it should be accessible both *inside* the code blocks that belong to the `if` and `else` statements, as well as *outside* of them.

The `out` keyword instructs the compiler that the `TryParse()` method will not only return a value the traditional way (as a return value), but also will communicate an output through this two-way parameter.

When you run the code, you should see the following output:

```Output
Measurement: 102
```

### Step 2 - Use the parsed int later in code

1. To demonstrate that the `result` that was declared earlier, then populated by the `out` parameter, is also usable later in your code, update your code in the Visual Studio Code Editor as follows:

    ```c#
    string value = "102";
    int result = 0;
    if (int.TryParse(value, out result))
    {
        Console.WriteLine($"Measurement: {result}");
    }
    else
    {
        Console.WriteLine("Unable to report the measurement.");
    }

    /* Since it is defined outside of the if statement, 
    it can be accessed later in your code. */
    Console.WriteLine($"Measurement (w/ offset): {50 + result}");
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
    Measurement: 102
    Measurement (w/ offset): 152
    ```

### Step 3 - Modify the string variable to an unparseable value

Lastly, let's look at the other scenario - where we intentionally give `TryParse()` a bad value that can't be converted into an `int`.

1. Modify the first line of code reinitializing the variable `value` to a different value.

    ```c#
    string value = "bad";
    ```

1. Also, modify the last line of code to ensure that the result is greater than 0 before showing the second message.

    ```c#
    if (result > 0)
        Console.WriteLine($"Measurement (w/ offset): {50 + result}");
    ```

1. The entire code example should now match the following code:

    ```c#
    string value = "bad";
    int result = 0;
    if (int.TryParse(value, out result))
    {
        Console.WriteLine($"Measurement: {result}");
    }
    else
    {
        Console.WriteLine("Unable to report the measurement.");
    }

    // Since it is defined outside of the if statement, 
    // it can be accessed later in your code.
    if (result > 0)
        Console.WriteLine($"Measurement (w/ offset): {50 + result}");
    ```

1. Save your code file, and then use Visual Studio Code to run your code. You should get the following result:

    ```Output
    Unable to report the measurement.
    ```

## Recap

The `TryParse()` method is a valuable tool. Here are few quick ideas to remember.

- Use `TryParse()` when converting a string into a numeric data type.
- `TryParse()` returns `true` if the conversion is successful, `false` if it's unsuccessful.
- An out parameter provides a secondary means of a method returning a value. In this case, the out parameter returns the converted value.
- Use the keyword `out` when passing in an argument to a method that has defined an out parameter.

## Check your knowledge

## Multiple Choice

Which technique should be used to change `myInput`, a `string` value `"2.71828"`, into a `decimal` variable `myInputDecimal`?
( ) `decimal myInputDecimal = (decimal)(myInput);` {{That's incorrect. A `string` cannot be cast into a `decimal`.}}
( ) `decimal myInputDecimal = myInput + 0;` {{That's incorrect. A `string` cannot be implicitly converted into a `decimal`.}}
(x) `decimal.TryParse(myInput, out myInputDecimal)` {{That's correct. Using `TryParse` (or `Parse()`) is a valid technique.}}

## Multiple Choice

Which best describes the return type of `decimal.TryParse()`?
( ) `decimal` {{That's incorrect. `TryParse()` returns a `bool` }}
(x) `bool` {{That's correct. `TryParse()` returns a `bool` }}
( ) `out` {{That's incorrect. `TryParse()` returns a `bool`. `out` is a parameter used in `TryParse()` for signifying the output variable to use.}}
