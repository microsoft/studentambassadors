Code challenges throughout these modules will reinforce what you've learned and help you gain some confidence before continuing on.

## Fix this code

Use what you've learned about code blocks and variable scope in this module to fix the poorly written code sample provided. There are many improvements that you can make. Good luck!

## Code challenge: update problematic code in the code editor

1. Ensure that you have an empty Program.cs file open in Visual Studio Code.

    If necessary, open Visual Studio Code, and then complete the following steps to prepare a Program.cs file in the Editor:

    1. On the **File** menu, select **Open Folder**.

    1. Use the Open Folder dialog to navigate to, and then open, the **CsharpProjects** folder.

    1. In the Visual Studio Code EXPLORER panel, select **Program.cs**.

    1. On the Visual Studio Code **Selection** menu, select **Select All**, and then press the Delete key.

1. Type the following code into the Visual Studio Code Editor.

    ```c#
    using System;
    
    int[] numbers = { 4, 8, 15, 16, 23, 42 };
    
    foreach (int number in numbers)
    {
        int total;
        
        total += number;
    
        if (number == 42)
        {
           bool found = true;
    
        }
    
    }
    
    if (found) 
    {
        Console.WriteLine("Set contains 42");
    
    }
    
    Console.WriteLine($"Total: {total}");
    ```

1. Review the intended output.

    When you have completed the required code edits, your application should produce the following output:

    ```Output
    Set contains 42
    Total: 108
    ```

1. Complete the code updates required so that the existing `Console.WriteLine()` statements produce the desired output.

    Variable scope may need to be adjusted.

1. Optimize your code for readability.

    Depending on the amount of whitespace that you include and some other factors, you should have around 17 lines of code.  

Whether you get stuck and need to peek at the solution or you finish successfully, continue on to view a solution to this challenge.
