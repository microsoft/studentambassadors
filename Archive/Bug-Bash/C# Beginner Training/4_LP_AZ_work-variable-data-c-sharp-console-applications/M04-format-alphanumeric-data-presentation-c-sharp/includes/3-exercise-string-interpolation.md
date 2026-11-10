---
title: Exercise - Explore string interpolation
durationInMinutes: 8
---

Suppose we want to print a receipt for the sale of a chemical solvent used in industrial settings. While our scales measure in micrograms, we price each sale in milligrams (a thousandth of a gram). To print the receipt, we would likely need to combine data of different types, including fractional values, currency, and percentages in precise ways.

### Step 1 - Display the invoice number using string interpolation

1. Select and delete all code lines in the Visual Studio Code Editor.

1. Update your code in the Visual Studio Code Editor as follows:

    ```c#
    int invoiceNumber = 1201;
    decimal productMeasurement = 25.4568m;
    decimal subtotal = 2750.00m;
    decimal taxPercentage = .15825m;
    decimal total = 3185.19m;

    Console.WriteLine($"Invoice Number: {invoiceNumber}");
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
    Invoice Number: 1201
    ```
    >[!NOTE]
    > You may see several warnings such as `warning CS0219: The variable 'productMeasurement' is assigned but its value is never used` for all the varibles that were defined but not yet used in the code.

### Step 2 - Display the product measurement in milligrams

Since we bill our customers using milligrams even though our measuring instruments measure to the precision of a microgram, we will only display three digits after the decimal point.

1. Add the following code below the code you typed in step 1:

    ```c#
    Console.WriteLine($"   Measurement: {productMeasurement:N3} mg");
    ```

1. Save your code file, and then use Visual Studio Code to run your code. When you run the code, you should see the following output:

    ```Output
    Invoice Number: 1201
       Measurement: 25.457 mg
    ```

### Step 3 - Display the subtotal that we'll charge the customer formatted as currency

1. Add the following code below the code you typed in steps 1 and 2:

    ```c#
    Console.WriteLine($"     Sub Total: {subtotal:C}");
    ```

1. Save your code file, and then use Visual Studio Code to run your code. When you run the code, you should see the following output:

    ```Output
    Invoice Number: 1201
    Measurement: 25.457 mg
        Sub Total: ¤2,750.00
    ```

### Step 4 - Display the tax charged on the sale formatted as a percentage

1. Add the following code below the code you typed in steps 1 through 3:

    ```c#
    Console.WriteLine($"           Tax: {taxPercentage:P2}");
    ```

1. Save your code file, and then use Visual Studio Code to run your code. When you run the code, you should see the following output:

    ```Output
    Invoice Number: 1201
    Measurement: 25.457 mg
        Sub Total: ¤2,750.00
            Tax: 15.83 %
    ```

## Step 5 - Finalize the receipt with the total amount due formatted as currency.

1. Add the following code below the code you typed in steps 1 through 4:

    ```c#
    Console.WriteLine($"     Total Due: {total:C}");
    ```

1. The entire code for the exercise should match as follows:

    ```c#
    int invoiceNumber = 1201;
    decimal productMeasurement = 25.4568m;
    decimal subtotal = 2750.00m;
    decimal taxPercentage = .15825m;
    decimal total = 3185.19m;

    Console.WriteLine($"Invoice Number: {invoiceNumber}");
    Console.WriteLine($"   Measurement: {productMeasurement:N3} mg");
    Console.WriteLine($"     Sub Total: {subtotal:C}");
    Console.WriteLine($"           Tax: {taxPercentage:P2}");
    Console.WriteLine($"     Total Due: {total:C}");
    ```

1. Save your code file, and then use Visual Studio Code to run your code. When you run the code, you should see the following output:

    ```Output
    Invoice Number: 1201
    Measurement: 25.457 mg
        Sub Total: ¤2,750.00
            Tax: 15.83 %
        Total Due: ¤3,185.19
    ```
