Unit Title: Exercise - Write code to display all ourAnimals array data
-----------------------------------------------------------------------------------------------------------------------------------------------

In this step of our development process, we will write the nested looping structure and conditional code block that will be used to display all of the information in the ourAnimals array. The detailed tasks that we will complete during this exercise are:

1. Outer loop: build the outer loop that iterates through the animals in the ourAnimals array.
1. Data check: write code that checks for existing pet data and displays the pet ID if data exists for a pet.
1. Inner loop: build an inner loop that displays all of the pet characteristics for pets with data assigned.
1. Verification test: perform verification tests for the code that you have developed in this exercise.

> [!IMPORTANT]
> You must complete the previous exercise in this module before starting this exercise.

## Build a loop to iterate through the ourAnimals array

In this task, we will create the outer `for` loop that's used to iterate through the animals in the `ourAnimals` array. We will examine the relationship between the dimensions of our array and the parameters of our for loop, and we will consider the differences between using `for` statements and `foreach` statements when working with multidimensional arrays. Let's get started.

1. Ensure that you have Visual Studio Code open, and that your Program.cs file is visible in the Editor.

1. Inside the code block for the `switch(menuSelection)` selection statement, locate the following code lines:

    ```c#
    case "1":
        // List all of our current pet information
        Console.WriteLine("this app feature is coming soon - please check back to see progress.");
        Console.WriteLine("Press the Enter key to continue.");
        readResult = Console.ReadLine();
        break;
    ```

1. Delete the `Console.WriteLine()` statement used to display the "coming soon" message, and leave a blank code line below the `// List all of our current pet information` code comment line.

    The feedback message will not be needed because we will be displaying the contents of the ourAnimals array. As you develop the code corresponding to the other menu selections, those feedback messages will be removed/replaced as well.

    Leave the message that says `Press the Enter key to continue.`

1. Starting on the blank code line that you created, begin a `for` statement as follows:

    ```c#
    for ()
    {
    }
    ```

1. Take a minute to consider the purpose of this `for` statement and how that "purpose" affects the values that we assign to the _for initializer_, _for condition_, and _for iterator_.

    Recall that a `for` statement has three parts that control how it implements iterations: the _for initializer_; the _for condition_, and the _for iterator_.

    We want our `for` loop to help us iterate through our array. We know that arrays are zero indexed, meaning that an array with n elements is indexed from 0 to n-1. So we want a _for initializer_, _for condition_, and _for iterator_ that establish the same conditions. In other words, we want our for loop to start at 0, increment by 1, and end at maxPets-1.

    Our ourAnimals array is declared as follows: `string[,] ourAnimals = new string[maxPets, 6];`. We know that the value assigned to maxPets is 8. In this declaration, maxPets specifies the number of items in the first dimension of the array, not the zero-based index number that we use to reference items in the array. Once again, although maxPets = 8, the array index numbers range from 0 to 7.

1. To specify the control value of our `for` loop, update your code as follows:

    ```c#
    for (int i = 0; i < maxPets; i++)
    {
    }
    ```

    As we can see, our _for initializer_ of `int i = 0;` aligns with our zero indexed array, our _for condition_ of `i < maxPets;` aligns with the first dimension of our array, and the _for iterator_ of `i++` will increment our loop control value by 1 as our loop iterates.

1. Take a minute to consider our choice to use a `for` statement rather than a `foreach` statement to loop through the ourAnimals array.

    Given that we want to iterate through each animal in the ourAnimals array one at a time, why don't we use a foreach loop? After all, we've seen that the `foreach` statement is designed for cases when we want to iterate through each item in an array of items.
 
    The reason why we don't use a `foreach` loop in this situation is because the ourAnimals array is multidimensional array (a multidimensional string array in this case). Since ourAnimals is a multidimensional array, each element contained within ourAnimals is a separate item of type string. If we used a foreach loop to iterate through ourAnimals, it would recognize each string as a separate item in a list of 48 string items (8 x 6 = 48) rather than considering the two array dimensions separately. In other words, the foreach loop will not recognize 8 rows of items, where each row contains a column of 6 items. Since we want to work with one animal at a time, processing the values of all six animal characteristics when we work on that animal, the foreach is not the right choice.

    That said, if the ourAnimals array was a jagged array configured as an array of string arrays, we could use a foreach for both the outer and inner loops. The outer loop would iterate through the string array elements in the jagged array (the "rows"), and inner loop would iterate through the strings in the string arrays (the "columns").

    The following example demonstrates the jagged array approach.

    ```c#
    string[][] jaggedArray = new string[][]
    {
        new string[] { "one1", "two1", "three1", "four1", "five1", "six1" },
        new string[] { "one2", "two2", "three2", "four2", "five2", "six2" },
        new string[] { "one3", "two3", "three3", "four3", "five3", "six3" },
        new string[] { "one4", "two4", "three4", "four4", "five4", "six4" },
        new string[] { "one5", "two5", "three5", "four5", "five5", "six5" },
        new string[] { "one6", "two6", "three6", "four6", "five6", "six6" },
        new string[] { "one7", "two7", "three7", "four7", "five7", "six7" },
        new string[] { "one8", "two8", "three8", "four8", "five8", "six8" }
    };

    foreach (string[] array in jaggedArray)
    {
        foreach (string value in array)
        {
            Console.WriteLine(value);
        }
        Console.WriteLine();
    }
    ```

    In cases like our Contoso Pets app, it is probably easier to use a multidimensional string array and nested `for` loops rather than a jagged array and nested `foreach` loops, but now that you see how each option could work in this app, you can make your own choice in future coding projects.

1. On the Visual Studio Code **File** menu, select **Save**.

1. Open the Integrated Terminal panel in Visual Studio Code and enter the command to Build your program.

    To open the Integrate Terminal from the EXPLORER view, right-click **Starter**, and then select **Open in Integrated Terminal**. You can also use the **View** or **Terminal** menu to open the Integrated Terminal panel.

    To Build your program, enter the `dotnet build` command from the Terminal command prompt.

1. Fix any build errors or warnings that you see reported before continuing.

    Remember that the Build error and warning messages tell you what the issue is and where you can find it. When resolving issues, it is best to start with the issues that occur near the top of your code and work down.

1. Close the Terminal panel.

## Check for existing pet data and display result

In this task, we will use an `if` statement to find each pet in the ourAnimals array that has been assigned pet characteristics data. When a pet with assigned data is found, we will display the petID. When there is no data assigned, nothing should be displayed. We will run the code to verify that our `for` and `if` statements are working correctly. Let's get started.

1. Create a blank code line inside your `for` statement code block as follows:

    ```c#
    for (int i = 0; i < maxPets; i++)
    {

    }    
    ```

1. To create an `if` statement that checks for pet ID data, update your code as follows:

    ```c#
    for (int i = 0; i < maxPets; i++)
    {
        if (ourAnimals[i, 0] != "ID #: ")
        {
        }
    }    
    ```

1. Take a minute to consider what this `if` statement is evaluating and why.

    There is plenty to consider here. Let's take it one step at a time.

    First, let's look at the left side of our expression: `ourAnimals[i, 0]`. Notice that we are using our loop control variable `i` to specify which pet/animal in our array we are currently working on within our loop. As you may recall, the `0` in `[i, 0]` corresponds to the petID characteristic. Since the first dimension of in our array corresponds to the "number" of the animal, this side of the expression ensures that we are checking the value assigned to petID for each animal, or "row", of the array.

    Next, let's consider our choice of comparison operator. Notice that we have chosen to use the not-equal operator, `!=`. This choice means that our expression will be evaluated as `true` whenever the value assigned to petID, `ourAnimals[i, 0]`, is NOT equal to the value listed on the right side of the equation.

    Finally, let's look at the value on the right side of our equation. Notice that we specify a static string value of `"ID #: "`. As you may recall, this value is the default value that we assign to petID when we generate our sample dataset. When a pet has its characteristics defined, the petID value is updated, and will NOT be equal to the default value.

    So, our `if` statement will evaluate as `true` when the pet ID has been assigned a value (when pet ID is NOT equal to the default value).

    Why are we using this expression here? When a pet ID is assigned, the default value will be appended with a calculated value such as d1, d2, c3. In this case, we don't care what the value of pet ID is as long as it isn't equal to the default value!  

1. To create a `Console.WriteLine()` method that displays the petID value when pet data is found, update your code as follows:

    ```c#
    for (int i = 0; i < maxPets; i++)
    {
        if (ourAnimals[i, 0] != "ID #: ")
        {
            Console.WriteLine(ourAnimals[i, 0]);
        }
    }    
    ```

    Notice that we pass our array element specification to the WriteLine() method directly.

1. On the Visual Studio Code **File** menu, select **Save**.

1. Open the Integrated Terminal panel and enter the command to Build your program.

1. Fix any build errors or warnings that you see reported before continuing.

1. At the Terminal command prompt, enter the command to run your program.

    Enter the `dotnet run` command at the Terminal command prompt to run your program code.

    You should see menu options display in the Terminal as you did before.

    If your code generates runtime errors on startup, which is unlikely if your build succeeded, review your code to identify and fix the errors. You will need to save your updates and then rebuild and rerun your program.

1. At the Terminal command prompt, to verify that your new code logic is working as expected, enter **1**

    You should see the following petID values displayed (the IDs of the four pets that have been assigned data).

    ```txt
    ID #: d1
    ID #: d2
    ID #: c3
    ID #: c4
    Press the Enter key to continue.
    ```

    If your code is displaying different output when you select menu option 1, review and update your code. Remember that you need to Save your Program.cs file and re-Build your code after making updates before the changes will appear in your running program.

1. Exit the application, and then close the Terminal panel.

## Display all pet characteristics for pets with data assigned

In this task, we will create a `for` loop inside the `if` statement code block that will be used to display all of the characteristics of the current pet. Let's get started.

1. In the code Editor, locate the following code lines in your Program.cs file:

    ```c#
    for (int i = 0; i < maxPets; i++)
    {
        if (ourAnimals[i, 0] != "ID #: ")
        {
            Console.WriteLine(ourAnimals[i, 0]);
        }
    }    
    ```

1. To create the `for` loop that will iterate through the characteristics of each pet, update your code as follows:

    ```c#
    for (int i = 0; i < maxPets; i++)
    {
        if (ourAnimals[i, 0] != "ID #: ")
        {
            Console.WriteLine(ourAnimals[i, 0]);
            for (int j = 0; j < 6; j++)
            {
            }
        }
    }    
    ```

    Notice that we now have a second (inner) `for` loop that is "nested" within the first (outer) `for` loop. As we know, the outer loop iterates through the animals in our array. Our intention is for the inner loop to iterate through the characteristics of each animal. Since we have a multidimensional array, it will be easy to implement the code that accesses animal characteristics in an upcoming step.
  
1. Take a minute to review the expression that we use in the `for` statement that we just added.

    Notice that our loop control variable is named `j`. When nesting `for` loops, one conventional approach is to use `i` in the outer loop and `j` in the inner loop. Following conventions like this makes it easier for others to read your code.

    Also notice that since we store 6 characteristics, our _for initializer_ is `int j = 0;` and our _for condition_ is `j < 6;`. This combination of initializer and condition matches the array index range that we need, 0-5.

1. To display each characteristic of a pet on a separate line, update your code as follows:

    ```c#
    for (int i = 0; i < maxPets; i++)
    {
        if (ourAnimals[i, 0] != "ID #: ")
        {
            Console.WriteLine(ourAnimals[i, 0]);
            for (int j = 0; j < 6; j++)
            {
                Console.WriteLine(ourAnimals[i, j]);
            }
        }
    }    
    ```

1. Take a minute to consider nested structure that we've created and the displayed output that this code will produce.

    Notice that the value we are writing to the console, `ourAnimals[i, j]`, uses the loop control variables from both the outer and inner `for` loops.

    We have already seen that the first dimension of the ourAnimals array corresponds to the different pets, and that the second dimension corresponds to the characteristics of each pet. We have also seen that the `if` statement will prevent the inner loop from running if there is no pet data assigned to the current pet. We also know that the inner loop will complete all of its iterations for each iteration of the outer loop. Therefore, we know that each animal's characteristics will be displayed as intended.

1. To replace the petID message with a blank WriteLine, update your code as follows:

    ```c#
    for (int i = 0; i < maxPets; i++)
    {
        if (ourAnimals[i, 0] != "ID #: ")
        {
            Console.WriteLine();
            for (int j = 0; j < 6; j++)
            {
                Console.WriteLine(ourAnimals[i, j]);
            }
        }
    }    
    ```

    This final update will make it easier to see the separation between pets when our output is displayed to the console (Terminal).

1. On the Visual Studio Code **File** menu, select **Save**.

1. Open a Terminal pane and Build the program.

1. Fix any build errors or warnings that you see reported before continuing.

## Check your work

In this task, we will run our application from the Integrated Terminal and verify that our nested combination of `for` and `if` statements is producing the expected results. Let's get started.

1. If necessary, open Visual Studio Code's Integrated Terminal panel.

1. At the Terminal command prompt, enter **dotnet run**

1. At the Terminal command prompt, enter **1**

1. Verify that the pet data is displayed for the four pets that have been assigned data.

    ```txt
    ID #: d1
    Species: dog
    Age: 2
    Nickname: lola
    Physical description: medium sized cream colored female golden retriever weighing about 65 pounds. housebroken.
    Personality: loves to have her belly rubbed and likes to chase her tail. gives lots of kisses.

    ID #: d2
    Species: dog
    Age: 9
    Nickname: loki
    Physical description: large reddish-brown male golden retriever weighing about 85 pounds. housebroken.
    Personality: loves to have his ears rubbed when he greets you at the door, or at any time! loves to lean-in and give doggy hugs.

    ID #: c3
    Species: cat
    Age: 1
    Nickname: Puss
    Physical description: small white female weighing about 8 pounds. litter box trained.
    Personality: friendly

    ID #: c4
    Species: cat
    Age: ?
    Nickname:
    Physical description:
    Personality:
    Press the Enter key to continue.
    ```

    > [!NOTE]
    > If your don't see the expected results displayed, check to be sure that you saved your updated Program.cs file. If you Save additional changes to your code, you will need to re-Build your project before you try running it again. If you are not seeing the expected results, and can't identify the issue, you can examine the Program.cs code in the Final folder. The Final folder is included as part of the download you completed during Setup. We recommend that you spend time trying to identify and fix syntax and logic issue in your code before checking the Program.cs file in the Final folder.

1. Exit the application, and then close the Terminal panel.
