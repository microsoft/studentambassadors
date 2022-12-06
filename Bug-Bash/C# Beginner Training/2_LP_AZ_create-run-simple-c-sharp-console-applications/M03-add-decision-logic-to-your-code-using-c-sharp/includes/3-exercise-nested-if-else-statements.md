---
title:  Exercise - Nested if and else statements
durationInMinutes: 3
---
Previously, we used multiple `if` statements to implement the rules of our game. However, when we left off in the previous unit, there was opportunity for improvement -- improvement to the expressiveness of the code and improvement to fix a subtle bug in our code.

## Improve code and fix a bug by adding else and else-if statements

Next, we'll use variants of the `if` statement to improve our code and fix a logic bug.

### Step 1 - Use if and else statements instead of two separate if statements

Instead of performing two checks to display the "You win!" or "Sorry, you lose" message, we'll use the `else` keyword.

1. Ensure that you have an empty Program.cs file open in Visual Studio Code.

    If necessary, open Visual Studio Code, and then complete the following steps to prepare a Program.cs file in the Editor:

    1. On the **File** menu, select **Open Folder**.

    1. Use the Open Folder dialog to navigate to, and then open, the **CsharpProjects** folder.

    1. In the Visual Studio Code EXPLORER panel, select **Program.cs**.

    1. On the Visual Studio Code **Selection** menu, select **Select All**, and then press the Delete key.

1. Modify your code to match the following code listing:

    ```c#
    Random dice = new Random();
    
    int roll1 = dice.Next(1, 7);
    int roll2 = dice.Next(1, 7);
    int roll3 = dice.Next(1, 7);
    
    int total = roll1 + roll2 + roll3;
    
    Console.WriteLine($"Dice roll: {roll1} + {roll2} + {roll3} = {total}");
    
    if ((roll1 == roll2) || (roll2 == roll3) || (roll1 == roll3))
    {
        Console.WriteLine("You rolled doubles!  +2 bonus to total!");
        total += 2;
    }
    
    if ((roll1 == roll2) && (roll2 == roll3))
    {
        Console.WriteLine("You rolled triples!  +6 bonus to total!");
        total += 6;
    }
    
    if (total >= 15)
    {
        Console.WriteLine("You win!");
    }
    else 
    {
        Console.WriteLine("Sorry, you lose.");
    }
    
    ```

    Here, if `total >= 15` is false, then the code block following the `else` keyword will execute. Because our two outcomes are related opposites, this is a perfect scenario for the `else` keyword.

### Step 2 - Modify the code to remove the stacking bonus for doubles and triples using nesting

In the previous unit, we saw how we introduced a subtle logic bug into our application. Let's fix that issue by nesting our `if` statements.

Nesting allows us to place code blocks inside of code blocks. In this case, we'll nest `if` and `else` statements (the check for triples) inside of another `if` statement (the check for doubles) to prevent them both from happening.

1. Modify your code to match the following code listing:

    ```c#
    Random dice = new Random();
    
    int roll1 = dice.Next(1, 7);
    int roll2 = dice.Next(1, 7);
    int roll3 = dice.Next(1, 7);
    
    int total = roll1 + roll2 + roll3;
    
    Console.WriteLine($"Dice roll: {roll1} + {roll2} + {roll3} = {total}");
    
    if ((roll1 == roll2) || (roll2 == roll3) || (roll1 == roll3))
    {
        if ((roll1 == roll2) && (roll2 == roll3))
        {
            Console.WriteLine("You rolled triples!  +6 bonus to total!");
            total += 6;
        }
        else
        {
            Console.WriteLine("You rolled doubles!  +2 bonus to total!");
            total += 2;
        }
    }
    
    if (total >= 15)
    {
        Console.WriteLine("You win!");
    }
    else 
    {
        Console.WriteLine("Sorry, you lose.");
    }
    
    ```

1. Take a minute to review the nested `if` statements.

    Our goal is to create an inner `if-else` construct where the two outcomes are related opposites, and then use the opposing outcomes (if/true and else/false) to award the bonus points for triples and doubles. To achieve our goal we check for doubles in the outer `if` statement, and then triples in inner `if` statement. This pattern ensures that when our inner check for triples returns `false`, our `else` code block can award the points for doubles.

    We will "hard-code" the results of our three rolls in order to test our code logic.

1. Create a blank code line above the line where `total` is declared and initialized.

1. To test for a roll of doubles, enter the following code:

    ```c#
    roll1 = 6;
    roll2 = 6;
    roll3 = 5;
    ```

    Hard-coding the three `roll` variables enables us to test the code without having to run the application dozens of times.

1. On the Visual Studio Code **File** menu, click **Save**.

1. In the EXPLORER panel, to open a Terminal at your TestProject folder location, right-click **TestProject**, and then select **Open in Integrated Terminal**.

    A Terminal panel should open, and should include a command prompt showing that the Terminal is open to your TestProject folder location.

1. At the Terminal command prompt, to run your code, type **dotnet run** and then press Enter.

    When your code runs, you should see:

    ```Output
    Dice roll: 6 + 6 + 5 = 17
    You rolled doubles!  +2 bonus to total!
    You win!
    
    ```

1. To test for a roll of triples, update your hard-coded roll variables as follows:

    ```c#
    roll1 = 6;
    roll2 = 6;
    roll3 = 6;
    ```

1. On the Visual Studio Code **File** menu, click **Save**.

1. In the EXPLORER panel, to open a Terminal at your TestProject folder location, right-click **TestProject**, and then select **Open in Integrated Terminal**.

1. At the Terminal command prompt, to run your code, type **dotnet run** and then press Enter.

    When your code runs, you should see:

    ```Output
    Dice roll: 6 + 6 + 6 = 18
    You rolled triples!  +6 bonus to total!
    You win!
    
    ```

### Step 3 - Use if, else, and else if statements to give a prize instead of a win-lose message

To make the game more fun, let's change the game from win-or-lose to award fictitious prizes for each score. We'll offer four prizes. The player should win only one prize:

- If the player scores greater or equal to 16, they'll win a new car.
- If the player scores greater or equal to 10, they'll win a new laptop.
- If the player scores exactly 7, they'll win a trip.
- Otherwise, the player wins a kitten.

1. Modify the code from the previous steps to the following code listing:

    ```c#
    Random dice = new Random();
    
    int roll1 = dice.Next(1, 7);
    int roll2 = dice.Next(1, 7);
    int roll3 = dice.Next(1, 7);
    
    int total = roll1 + roll2 + roll3;
    
    Console.WriteLine($"Dice roll: {roll1} + {roll2} + {roll3} = {total}");
    
    if ((roll1 == roll2) || (roll2 == roll3) || (roll1 == roll3))
    {
        if ((roll1 == roll2) && (roll2 == roll3))
        {
            Console.WriteLine("You rolled triples!  +6 bonus to total!");
            total += 6;
        }
        else
        {
            Console.WriteLine("You rolled doubles!  +2 bonus to total!");
            total += 2;
        }
    }
    
    if (total >= 16)
    {
        Console.WriteLine("You win a new car!");
    }
    else if (total >= 10)
    {
        Console.WriteLine("You win a new laptop!");
    }
    else if (total == 7)
    {
        Console.WriteLine("You win a trip for two!");
    }
    else
    {
        Console.WriteLine("You win a kitten!");
    }
    
    ```

1. Take a minute to review the updated `if-elseif-else` construct.

    The `if`, `else if`, and `else` statements allow you to create multiple exclusive conditions as Boolean expressions. In other words, when you only want one outcome to happen, but you have several possible conditions and results, use as many `else if` statements as you want. If none of the `if` and `else if` statements apply, the final `else` code block will be executed. The `else` is optional, but it must come last if you choose to include it.

1. Use the technique of temporarily hard-coding the `roll` variables to test each message.

## Recap

- The combination of `if` and `else` statements allows you to test for one condition, and then perform one of two outcomes. The code block for the `if` will be run when the Boolean expression is `true`, and the code block for the `else` will be run when the Boolean expression is `false`.
- You can nest `if` statements to narrow down a possible condition. However, you should consider using the `if`, `else if`, and `else` statements instead.
- Use `else if` statements to create multiple exclusive conditions.
- An `else` is optional, but it must always come last when included.
