---
title: Exercise - Use the string's IndexOf() and Substring() helper methods
durationInMinutes: 25
---

Let's begin by accessing parts of a string by identifying the position of one or more characters. Once you have located the position, you can then extract a specific part of the string.

## Exercise - Use the string's IndexOf() and Substring() helper methods

In this exercise, you'll use the `IndexOf()` method and its variants including `IndexOfAny()` and `LastIndexOf()` to locate the position of one character or string inside a larger string.

Once we've located the position, we can use the `Substring()` method to return the rest of the string after the position.

Or we can use an overloaded version of the `Substring()` method to set the number of characters (length) to return after the position.

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

### Step 1 - Write code to find an opening and closing parenthesis embedded in a string

1. Ensure that you have Visual Studio Code open and Program.cs displayed in the Editor panel.

    > [!NOTE]
    > Program.cs should be empty. If if isn't, select and delete all code lines.

1. Type the following code into the Visual Studio Code Editor:

    ```c#
    string message = "Find what is (inside the parentheses)";

    int openingPosition = message.IndexOf('(');
    int closingPosition = message.IndexOf(')');

    Console.WriteLine(openingPosition);
    Console.WriteLine(closingPosition);
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
    13
    36
    ```

In this case, the index of the `(` character is 13. Remember, these values are zero-based, so it's the 14th character in the string. The index of the `)` character is `36`.

Now that we have the two indexes, we can use them as the boundaries to retrieve the value between them.

### Step 2 - Add code to retrieve the value between two parenthesis characters

1. Update your code in the Visual Studio Code Editor as follows:

    ```c#
    string message = "Find what is (inside the parentheses)";

    int openingPosition = message.IndexOf('(');
    int closingPosition = message.IndexOf(')');

    // Console.WriteLine(openingPosition);
    // Console.WriteLine(closingPosition);

    int length = closingPosition - openingPosition;
    Console.WriteLine(message.Substring(openingPosition, length));
    ```

1. Save your code file, and then use Visual Studio Code to run your code. You should see the following output:

    ```Output
    (inside the parentheses
    ```

The `Substring()` method needs the starting position and the number of characters, or length, to retrieve. So, we calculate the length in a temporary variable called `length`, and pass it with the `openingPosition` value to retrieve the string inside of the parenthesis.

The result is close, however the output includes the opening parenthesis. In this particular situation, this is not desired. To fix this, we'll have to update our code to skip the index of the parenthesis itself.

### Step 3 - Update the code to modify the starting position of the sub string

1. Update your code in the Visual Studio Code Editor as follows:

    ```c#
    string message = "Find what is (inside the parentheses)";

    int openingPosition = message.IndexOf('(');
    int closingPosition = message.IndexOf(')');

    openingPosition += 1;

    int length = closingPosition - openingPosition;
    Console.WriteLine(message.Substring(openingPosition, length));
    ```

1. Save your code file, and then use Visual Studio Code to run your code. You should see the following output:

    ```Output
    inside the parentheses
    ```

By increasing the `openingPosition` by `1`, we skip over the opening parenthesis character.

The reason we're using the value `1` is because that is the length of the character. If we were attempting to locate a value starting after a longer string, for example, `<div>` or `---`, we would use the length of that string instead.

The following snippet of code shows how to find the value inside an opening and closing `<span>` tag.

```c#
string message = "What is the value <span>between the tags</span>?";

int openingPosition = message.IndexOf("<span>");
int closingPosition = message.IndexOf("</span>");

openingPosition += 6;
int length = closingPosition - openingPosition;
Console.WriteLine(message.Substring(openingPosition, length));
```

In this case, we're adding `6` to the `openingPosition` as the offset to calculate the length of the sub string.

### Avoid magic values

Hardcoded strings like `"<span>"` in the previous code listing are known as "magic strings" and hardcoded numeric values like `6` are known as "magic numbers". These "Magic" values are undesirable for a number of reasons and you should try to avoid them if possible.

In this specific case, consider how your code might break if you hardcoded the string `"<span>"` multiple times in your code, but misspelled one instance of it as `"<sapn>"`. The compiler won't catch this at compile time because the value is in a string. The misspelling will likely cause problems at run time, and depending on the complexity of your code, it might be difficult to track down. Furthermore, if you change the string `"<span>"` to `"<div>"`, but forget to change the number `6`, then your code will produce undesirable results.

Instead, you should use a constant with the `const` keyword. A constant allows you to define and initialize a variable whose value can never be changed. You would then use that constant in the rest of the code whenever you needed that value. This ensures that the value is only defined once and misspelling the `const` variable will be caught by the compiler.

The following code listing is a much safer way to write the same code.

```c#
string message = "What is the value <span>between the tags</span>?";

const string openSpan = "<span>";
const string closeSpan = "</span>";

int openingPosition = message.IndexOf(openSpan);
int closingPosition = message.IndexOf(closeSpan);

openingPosition += openSpan.Length;
int length = closingPosition - openingPosition;
Console.WriteLine(message.Substring(openingPosition, length));
```

This time, if the value of `openSpan` changes, the line of code that uses the `Length` property will be valid.

### Step 4 - Write code to retrieve the last occurrence of a sub string

Next, let's increase the complexity of the `message` variable by adding many sets of parentheses, then write code to retrieve the content inside the **last** set of parentheses.

1.	Update your code in the Visual Studio Code Editor as follows:

    ```c#
    string message = "(What if) I am (only interested) in the last (set of parentheses)?";
    int openingPosition = message.LastIndexOf('(');

    openingPosition += 1;
    int closingPosition = message.LastIndexOf(')');
    int length = closingPosition - openingPosition;
    Console.WriteLine(message.Substring(openingPosition, length));
    ```

1. Save your code file, and then use Visual Studio Code to run your code. You should see the following output:

    ```Output
    set of parentheses
    ```

The key to this example is the use of `LastIndexOf()`, which we use to get the positions of the last opening and closing parentheses.

### Step 5 - Update the code example to retrieve any value between one or more sets of parentheses in a string

This time, we'll update the `message` to have three sets of parentheses, and we'll write code to extract any text inside of them. We'll be able to reuse portions of our previous work, but will need to add a `while` statement to iterate through the string until all sets of parentheses are discovered, extracted, and displayed.

1.	Update your code in the Visual Studio Code Editor as follows:

    ```c#
    string message = "(What if) there are (more than) one (set of parentheses)?";
    while (true)
    {
        int openingPosition = message.IndexOf('(');
        if (openingPosition == -1) break;

        openingPosition += 1;
        int closingPosition = message.IndexOf(')');
        int length = closingPosition - openingPosition;
        Console.WriteLine(message.Substring(openingPosition, length));

        // Note how we use the overload of Substring to return only the remaining 
        // unprocessed message:
        message = message.Substring(closingPosition + 1);
    }
    ```

1. Save your code file, and then use Visual Studio Code to run your code. You should see the following output:

    ```Output
    What if
    more than
    set of parentheses
    ```

The key to understanding this technique is the last line of code inside the `while` loop.

```c#
message = message.Substring(closingPosition + 1);
```

When you use `Substring()` without specifying a length input parameter, it will return every character after the starting position you specify. We use this to our advantage, removing the first set of parentheses from the value of `message`. What remains is then processed in the next iteration of the `while` loop.

What happens during the final iteration when all that's left is the final `?` character?

That's addressed by the following lines of code:

```c#
int openingPosition = message.IndexOf('(');
if (openingPosition == -1) break;
```

The `IndexOf()` method will return `-1` if it can't find the input parameter in the string. We merely check for the value `-1` and `break` out of the loop.

Let's consider an even more advanced example. This time, we'll search for several different symbols -- not just a set of parentheses.

### Step 6 - Update the code example to work with different types of symbol sets

In this step the `message` string is updated, adding different types of symbols like square `[]` brackets and curly braces `{}`.To search for multiple symbols simultaneously we'll rely on `.IndexOfAny()`. We will search with `.IndexOfAny()` to return the index of the first symbol from the array `openSymbols` found in the `message` string.

Let's use `.IndexOfAny()` *without*, and then *with*, the starting position overload. Update your code in the Visual Studio Code editor as follows:

```c#
string message = "Help (find) the {opening symbols}";
Console.WriteLine($"Searching THIS Message: {message}");
char[] openSymbols = { '[', '{', '(' };
int startPosition = 6;
int openingPosition = message.IndexOfAny(openSymbols);
Console.WriteLine($"Found WITHOUT using startPosition: {message.Substring(openingPosition)}");

openingPosition = message.IndexOfAny(openSymbols, startPosition);
Console.WriteLine($"Found WITH using startPosition: {message.Substring(openingPosition)}");
```

Save your code file, and then use Visual Studio Code to run your code. You should see the following output:

```output
Searching THIS message: Help (find) the {opening symbols}
Found WITHOUT using startPosition: (find) the {opening symbols}
Found WITH using startPosition 6: {opening symbols}
```

Once we find a symbol, we'll need to find its matching closing symbol. Once we do that, the rest should look similar. We'll use a different tactic instead of modifying the original value of `message`. This time, we'll use the closing position of the previous iteration as the opening position of the current iteration.

1.	Update your code in the Visual Studio Code Editor as follows:

    ```c#
    string message = "(What if) I have [different symbols] but every {open symbol} needs a [matching closing symbol]?";

    // The IndexOfAny() helper method requires a char array of characters. 
    // We want to look for:

    char[] openSymbols = { '[', '{', '(' };

    // We'll use a slightly different technique for iterating through 
    // the characters in the string. This time, we'll use the closing 
    // position of the previous iteration as the starting index for the 
    //next open symbol. So, we need to initialize the closingPosition 
    // variable to zero:

    int closingPosition = 0;

    while (true)
    {
        int openingPosition = message.IndexOfAny(openSymbols, closingPosition);

        if (openingPosition == -1) break;

        string currentSymbol = message.Substring(openingPosition, 1);

        // Now we must find the matching closing symbol
        char matchingSymbol = ' ';

        switch (currentSymbol)
        {
            case "[":
                matchingSymbol = ']';
                break;
            case "{":
                matchingSymbol = '}';
                break;
            case "(":
                matchingSymbol = ')';
                break;
        }

        // To find the closingPosition, we use an overload of the IndexOf method to specify 
        // that our search for the matchingSymbol should start at the openingPosition in the string. 
        
        openingPosition += 1;
        closingPosition = message.IndexOf(matchingSymbol, openingPosition);

        // Finally, use the techniques we've already learned to display the sub-string:

        int length = closingPosition - openingPosition;
        Console.WriteLine(message.Substring(openingPosition, length));
    }
    ```

1. Save your code file, and then use Visual Studio Code to run your code. You should see the following output:

    ```Output
    What if
    different symbols
    open symbol
    matching closing symbol
    ```

In this example, we've added some comments to explain what's happening. Besides using `IndexOfAny()` to locate one of several possible symbols, the key is the following line of code:

```c#
closingPosition = message.IndexOf(matchingSymbol, openingPosition);
```

The variable `closingPosition` is used in the `Substring()` method, but is also used to find the next `openingPosition` value.

```c#
int openingPosition = message.IndexOfAny(openSymbols, closingPosition);
```

This is why the `closingPosition` variable is defined outside of the `while` loop and initialized to `0` for the first iteration.

## Recap

We covered a lot of ground in this unit. Here's the most important things to remember:

- `IndexOf()` gives us the first position of a character or string inside of another string.
- `IndexOf()` returns `-1` if it can't find a match.
- `Substring()` returns just the specified portion of a string, using a starting position and optional length.
- `LastIndexOf()` returns the last position of a character or string inside of another string.
- `IndexOfAny()` returns the first position of an array of `char` that occurs inside of another string.
- There's often more than one way to solve a problem. We used two separate techniques to find all instances of a given character or string.
- Avoid hardcoded magic values. Instead, define a `const` variable. A constant variable's value can't be changed after initialization.

## Check your knowledge

## Multiple Choice

What is the return value of `myString.IndexOf('C');` where `string myString = "C# Time";`?
(x) `0` {{That's correct. `"C"` is the first item in `myString` and matches at position `0`}}
( ) `1` {{That's incorrect. `1` is the second item in `myString`, the character `"#"`.}}
( ) `-1` {{That's incorrect. `-1` indicates no match is found in `myString`, and the first character in `myString` is the `"C"` match.}}
