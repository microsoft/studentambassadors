Code challenges throughout these modules will reinforce what you've learned, and help you gain some confidence before continuing on.

The focus of this challenge is to rewrite the code using a different technique to accomplish essentially the same task. This challenge will help you see the strengths/weaknesses of the switch-case when compared to an if-elseif-else statement.

## Look up product by SKU challenge

Suppose we work for a souvenir shop in a college town that sells t-shirts, sweatshirts, and other gifts with the school's logo and colors. The monthly sales report includes a product description and the Stock Keeping Unit (SKU) of the products sold. We've been asked to rewrite the code to make it more readable. The work has been broken down into tasks. One of the tasks is to update the code that converts a SKU into a description by using a `switch` statement (in place of an if-elseif-else construct).

## Code challenge: rewrite code to use a switch-case statement instead of an if-elseif-else statement

The code that you will start with converts a SKU into a long-form description (for example, the sku `01-MN-L` is a "large maroon sweat shirt").

Your challenge is to update the code to use a switch-statement. Running the code after your updates should produce the same result that the initial code produced.

1. Ensure that you have an empty Program.cs file open in Visual Studio Code.

    If necessary, open Visual Studio Code, and then complete the following steps to prepare a Program.cs file in the Editor:

    1. On the **File** menu, select **Open Folder**.

    1. Use the Open Folder dialog to navigate to, and then open, the **CsharpProjects** folder.

    1. In the Visual Studio Code EXPLORER panel, select **Program.cs**.

    1. On the Visual Studio Code **Selection** menu, select **Select All**, and then press the Delete key.

1. Enter the following code into the Editor panel.

    ```c#
    // SKU = Stock Keeping Unit
    string sku = "01-MN-L";
    
    string[] product = sku.Split('-');
    
    string type = "";
    string color = "";
    string size = "";
    
    if (product[0] == "01")
    {
        type = "Sweat shirt";
    } else if (product[0] == "02")
    {
        type = "T-Shirt";
    } else if (product[0] == "03")
    {
        type = "Sweat pants";
    }
    else
    {
        type = "Other";
    }
    
    if (product[1] == "BL")
    {
        color = "Black";
    } else if (product[1] == "MN")
    {
        color = "Maroon";
    } else
    {
        color = "White";
    }
    
    if (product[2] == "S")
    {
        size = "Small";
    } else if (product[2] == "M")
    {
        size = "Medium";
    } else if (product[2] == "L")
    {
        size = "Large";
    } else
    {
        size = "One Size Fits All";
    }
    
    Console.WriteLine($"Product: {size} {color} {type}");
    ```

1. Update the code to use a `switch` statement in place of the `if-elseif-else` statement.

    Use what you've learned about the `switch` statement to complete the update.

1. Verify that your output hasn't changed.

    No matter how you do it, your code should produce the following output.

    ```Output
    Product: Large Maroon Sweat shirt
    ```

Whether you get stuck and need to peek at the solution or you finish successfully, continue on to view a solution to this challenge.
