While string concatenation is simple and convenient, *string interpolation* is growing in popularity in situations where you need to combine many literal strings and variables into a single formatted message.

## What is string interpolation?

String interpolation combines multiple values into a single literal string by using a "template" and one or more *interpolation expressions*. An **interpolation expression** is a variable surrounded by an opening and closing curly brace symbol `{ }`. The literal string becomes a template when it's prefixed by the `$` character.

In other words, instead of writing the following line of code:

```c#
string message = greeting + " " + firstName + "!";
```

You can write this more concise line of code instead:

```c#
string message = $"{greeting} {firstName}!";
```

In this simple example, you save a few keystrokes. You can imagine how much more concise string interpolation can be in more complex operations. Moreover, many find the string interpolation syntax cleaner and easier to read.

In the following exercise, we'll rewrite the previous messages using string interpolation.

### Step 1: Delete all of the code in the code editor

Use your mouse to highlight all of the text in the code editor, then select the `backspace` or `del` key to remove everything.

### Step 2: Use string interpolation to combine a literal string and a variable value

To interpolate two strings together, you create a literal string and prefix the string with the `$` symbol. The literal string should contain at least one set of curly braces `{}` and inside of those characters you use the name of a variable.

Add the following code to the code window:

```c#
string firstName = "Bob";
string message = $"Hello {firstName}!";
Console.WriteLine(message);

```

Now, run the code. You'll see the following result in the output console:

```Output
Hello Bob!

```

### Step 3: Use string interpolation with multiple variables and literal strings

You can perform several interpolation operations in the same line of code.

Modify the code you wrote in Step 2 to the following code:

```c#
string firstName = "Bob";
string greeting = "Hello";
string message = $"{greeting} {firstName}!";
Console.WriteLine(message);

```

Now, run the code. You'll see the following result in the output console:

```Output
Hello Bob!

```

### Step 4: Avoid intermediate variables

Just as we did in the previous exercise, we can eliminate the temporary variable to store the message.

Modify the code you wrote in Step 3 to the following code:

```c#
string firstName = "Bob";
string greeting = "Hello";
Console.WriteLine($"{greeting} {firstName}!");

```

Now, run the code. The result in the output console should be the same, however we simplified the code:

```Output
Hello Bob!

```

### Step 5: Combine verbatim literals and string interpolation

Suppose you need to use a verbatim literal in your template. You can use both the verbatim literal prefix symbol `@` and the string interpolation `$` symbol together.

Delete the code from the previous steps, and type the following code into the .NET Editor.

```c#
string projectName = "First-Project";
Console.WriteLine($@"C:\Output\{projectName}\Data");

```

Now, run the code and you should see the following result.

```Output
C:\Output\First-Project\Data

```

## Recap

The primary ideas you should take away from this exercise:

- String interpolation provides an improvement over string concatenation by reducing the number of characters required in some situations.
- You can combine string interpolation and verbatim literals by combining the symbols for each and using that as a prefix for the string template.