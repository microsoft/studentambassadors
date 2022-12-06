Often times, you'll need to combine data from many different sources, including literal strings and variables containing both text and numeric data. In this module, you'll learn about two methods to accomplish this. In this unit, you'll use string concatenation to combine two or more values into a new string.

## What is string concatenation?

String concatenation is "programmer speak" for simply combining two or more values into a new value. Unlike addition, the second value is appended to the end of the first value, and so on. In the following exercise, you'll write code to concatenate values together.

### Step 1: Delete all of the code in the code editor

Use your mouse to highlight all of the text in the code editor, then select the `backspace` or `del` key to remove everything.

Later, we'll learn a different, less destructive technique for disabling the lines of code you no longer want to execute.

### Step 2: Concatenate a literal string and a variable

To concatenate two strings together, you use the *string concatenation operator*, which is the plus symbol `+`.

Add the following code to the code window:

```c#
string firstName = "Bob";
string message = "Hello " + firstName;
Console.WriteLine(message);

```

Now, run the code. You'll see the following result in the output console:

```Output
Hello Bob

```

Notice the order -- the first string `"Hello "` is first in the new string, and the value in the `firstName` variable is appended to the end of it.

### Step 3: Concatenate multiple variables and literal strings

You can perform several concatenation operations in the same line of code.

Modify the code you wrote in Step 2 to the following code:

```c#
string firstName = "Bob";
string greeting = "Hello";
string message = greeting + " " + firstName + "!";
Console.WriteLine(message);

```

Here we create a more complex message by combining several variables and literal strings.

Now, run the code. You'll see the following result in the output console:

```Output
Hello Bob!

```

### Step 4: Avoiding intermediate variables

In steps 2 and 3, we used an extra variable to hold the new string that resulted from the concatenation operation. Unless you have a good reason to do so, you can (and should) avoid using intermediate variables by performing the concatenation operation as you need it.

Modify the code you wrote in Step 3 to the following code:

```c#
string firstName = "Bob";
string greeting = "Hello";
Console.WriteLine(greeting + " " + firstName + "!");

```

Now, run the code. The result in the output console should be the same, however we simplified the code:

```Output
Hello Bob!

```

## Recap

The primary ideas you should take away from this exercise:

- String concatenation allows you to combine smaller literal and variable strings into a single string.
- Avoid creating intermediate variables if adding them doesn't increase readability.