In this challenge, you'll write code that will use a formula to convert a temperature from degrees Fahrenheit to Celsius. You'll print the result in a formatted message to the user.

### Step 1: Delete all of the code in the .NET Editor from the earlier exercise

Select all of the code in the .NET Editor then select the `del` or backspace key to delete it.

### Step 2: Write code in the .NET Editor to calculate Celsius given the current temperature in Fahrenheit

Begin with this line of code:

```c#
int fahrenheit = 94;

```

To convert temperatures in degrees Fahrenheit to Celsius, first subtract 32, then multiply by five ninths (5 / 9).

### Step 3: Display the result of the temperature conversion in a formatted message

Finally, you'll combine the variables with literal strings passed into a series of `Console.WriteLine()` commands to form the complete message.

When you're finished, the message should resemble the following output:

```Ou
The temperature is 34.444444444444444444444444447 Celsius.

```

> [!NOTE]
> Admittedly, we would prefer to not see so many values after the decimal point. Ideally the value would be formatted to a single value after the decimal point: `34.4`. In the module "Format values for display using composite formatting and string interpolation in C#" we'll learn how to format numbers for proper display to the user.

Whether you get stuck and need to peek at the solution or you finish successfully, continue on to view a solution to this challenge.
