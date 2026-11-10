Unit Title: Build sample data and menu selection loops
-----------------------------------------------------------------------------------------------------------------------------------------------

In this first step of our development process, we'll review the code provided in the Starter project folder and then move on to some clean-up and preparatory tasks before we begin adding features to our app. Our code clean-up task involves updating the selection statement that's used when generating the sample data for our app. Our preparatory tasks will be to add a looping structure around our menu selection code, and to create a code branching structure that is based on the user's menu selections. The detailed tasks that we'll complete during this exercise are:

1. Code review: review the contents of the Program.cs file.
1. Sample data: convert the if-elseif-else structure to switch-case structure that improves readability.
1. Menu loop: enclose the main menu and menu item selection in a loop that iterates until the user enters "exit".
1. Menu selections: write the code for a switch-case structure that establishes separate code branches for each menu option.
1. Code branches: write placeholder within the menu item branches that provides user feedback until app features are developed.
1. Verification test: perform verification tests for the code that you've developed in this exercise.

## Review the contents of the Program.cs file

In this task, we'll review the code that's provided as a Starter project for this module. The Program.cs file contains a preliminary version of the application that we'll be working on. The code includes an initial attempt at generating sample data for the application, and it displays a list of menu options that define the main features of our application. Let's take a look.

1. Ensure that you have the **GuidedProject** folder open in Visual Studio Code.

    The **Prepare** unit (the previous unit in this module) includes a Setup section that describes the process for downloading the initial starting point for our Guided project and opening the folder Visual Studio Code. If necessary, go back and follow the Setup instructions.

1. In the **EXPLORER** view, expand the **Starter** folder, then select **Program.cs**.

    When you select the Program.cs file, the file contents will open in the main Editor area to the right of the EXPLORER.

    If the EXPLORER view isn't open, you can select/open the EXPLORER view from the Activity Bar on the far left side of VS Code. EXPLORER is the topmost icon on the Activity Bar.

1. Take a few minutes to review the code in the Program.cs file.

1. Notice that the top portion of your code begins with a `Using` statement and some variable declarations.  

    ``` c#
    using System;

    // the ourAnimals array will store the following: 
    string animalSpecies = "";
    string animalID = "";
    string animalAge = "";
    string animalPhysicalDescription = "";
    string animalPersonalityDescription = "";
    string animalNickname = "";

    // variables that support data entry
    int maxPets = 8;
    string? readResult;
    string menuSelection = "";

    // array used to store runtime data, there is no persisted data
    string[,] ourAnimals = new string[maxPets, 6];
    ```

    The `using` statement enables us to write code that implements members of the `System` namespace without requiring us to specify `System`. For example, our code can use the `Console.WriteLine()` method without having to specify `System.Console.WriteLine()`. Among other things, the `using` statement makes our code easier to read.

    Next, we see a comment line and a list of variables. These variables, `animalSpecies` through `animalNickname`, will be used to hold the values of the pet characteristics. A bit later in the code we will be assigning these values to a multidimensional string array named `ourAnimals`. Each of these variables is initialized to contain a zero length string `""`. The `ourAnimals` array is declared a little further down in the code (we'll get to it soon).

    The next group of variables is a mix of `string` and `int` variables that will be used help generate sample data, read user input, and establish exit criteria for our main program loop. One interesting thing that you may have noticed is the code line `string? readResult;`. When used in a variable declaration like this, the `?` character is used to define a nullable type of the corresponding non-nullable variable type. When reading user entered values with the `Console.ReadLine()` method, it's best to use a nullable type.

    The final variable is our two-dimensional string array named `ourAnimals`. Since we're not initializing the array, we use the `new` operator. The number of rows is defined by maxPets, which has been initialized to 8. The number of characteristics that we're storing is six, the string variables that we examined above.  

1. Scroll down to examine the `for` loop that contains an `if-elseif-else` selection construct within its code block.

    > [!NOTE]
    > If you see a `switch` statement instead of an `if-elseif-else` inside the code block of your `for` loop, ensure that you are reviewing the Program.cs file in the Starter folder, not the Program.cs file in the Final folder. You don't want to make changes to the the code in the Final folder because you may need to use it as a reference later in this module.

1. Notice that the `for` loop uses the `maxPets` variable to establish an upper bound on the number of iterations. Also notice that the `if-elseif-else` construct selectively branches our code so that we can define different pet characteristics for the pets in our sample data set.

    The `if-elseif-else` construct is used to define different values for the first four iterations of the `for` loop. After that fourth iteration, all characteristics are assigned an empty, or zero-length, string.

    The values of the animal characteristic variables are assigned to the ourAnimals array at the bottom of the `for` loop.

1. Scroll to the bottom of the code file, and then examine the code that's used to display the menu options and read the user selection.

1. Notice that we assign the value returned by the `Console.ReadLine()` method to the nullable string `readResult`.

    Using a nullable string is best practice for capturing input from the ReadLine() method. Once we verify that the input value isn't null, we assign the value to a standard string variable named `menuSelection`, which we can evaluate without a concern that it may contain a null value. Many methods that accept strings as an input parameter will throw an error if they passed a null value. If we don't follow this input pattern, the code compiler is like to generate a warning when we build our project.

    The final lines of our Program.cs file echo the menu option selection and then pause execution until the Enter key is pressed.

## Convert if statement to switch statement

In this task, we'll walk through the process of converting the existing `if-elseif-else` construct to a `switch-case` construct that improves the readability of our code. Let's get started.

1. Scroll up to the start of the `for` loop that we use to generate our sample data.

1. Notice that the `if-elseif-else` construct begins with the following `if` statement and code block:

    ```c#
    if (i == 0)
    {
        animalSpecies = "dog";
        animalID = "d1";
        animalAge = "2";
        animalPhysicalDescription = "medium sized cream colored female golden retriever weighing about 65 pounds. housebroken.";
        animalPersonalityDescription = "loves to have her belly rubbed and likes to chase her tail. gives lots of kisses.";
        animalNickname = "lola";
    }
    ```

1. Replace the initial `if` statement and code block with the following code:

    ```c#
    switch (i)
    {
        case 0:
            animalSpecies = "dog";
            animalID = "d1";
            animalAge = "2";
            animalPhysicalDescription = "medium sized cream colored female golden retriever weighing about 65 pounds. housebroken.";
            animalPersonalityDescription = "loves to have her belly rubbed and likes to chase her tail. gives lots of kisses.";
            animalNickname = "lola";
            break;

    ```

    This `case 0:` code will perform the same selection as the `if (i == 0)` selection that it replaces. You'll be making corresponding replacements to complete the conversion from `if-elseif-else` construct to a `switch-case` construct.

1. Notice that a red squiggly line symbol now appears under the `;` at the end of the `break` statement.

    We seem to have created a couple of issues, but do't worry, we'll fix them. Visual Studio Code helps us to spot issues in our code, so let's investigate what this squiggly line is alerting us to. First off, we haven't closed the code block for our `switch` statement. Also, we now have an `else if` without the `if`, which isn't allowed. We will fix each of these issues as we complete the process of converting to a `switch`.

1. Replace the `else if (i == 1)` statement and code block with the following code:

    ```c#
    case 1:
        animalSpecies = "dog";
        animalID = "d2";
        animalAge = "9";
        animalPhysicalDescription = "large reddish-brown male golden retriever weighing about 85 pounds. housebroken.";
        animalPersonalityDescription = "loves to have his ears rubbed when he greets you at the door, or at any time! loves to lean-in and give doggy hugs.";
        animalNickname = "loki";
        break;

    ```

1. Replace the `else if (i == 2)` statement and code block with the following code:

    ```c#
    case 2:
        animalSpecies = "cat";
        animalID = "c3";
        animalAge = "1";
        animalPhysicalDescription = "small white female weighing about 8 pounds. litter box trained.";
        animalPersonalityDescription = "friendly";
        animalNickname = "Puss";
        break;

    ```

1. Replace the `else if (i == 3)` statement and code block with the following code:

    ```c#
    case 3:
        animalSpecies = "cat";
        animalID = "c4";
        animalAge = "?";
        animalPhysicalDescription = "";
        animalPersonalityDescription = "";
        animalNickname = "";
        break;

    ```

1. Replace the `else` statement and code block with the following code:

    ```c#
    default:
        animalSpecies = "";
        animalID = "";
        animalAge = "";
        animalPhysicalDescription = "";
        animalPersonalityDescription = "";
        animalNickname = "";
        break;

    }
    ```

1. Notice that the `if-elseif-else` construct is now completely replaced by a `switch-case` construct and that the red squiggly line symbol is gone.

    If portions of your `if-elseif-else` construct still remain, or if your `switch` statement is incomplete, check your work to see if you missed a step.

1. Your completed `switch-case` construct should have a structure similar to the following code:

    > [!NOTE]
    > The variables that used to assign the pet characteristic values have been removed from the code sample below to shorten the number of code lines. Your code should include the string variable assignments for each case pattern, including the default case.

    ```c#
    switch (i)
    {
        case 0:
            // variable assignments were removed for this view of the structure
            break;

        case 1:
            // variable assignments were removed for this view of the structure
            break;

        case 2:
            // variable assignments were removed for this view of the structure
            break;

        case 3:
            // variable assignments were removed for this view of the structure
            break;

        default:
            // variable assignments were removed for this view of the structure
            break;
    }
    ```

    Recall that execution of a switch section isn't permitted to “fall through” to the next switch section. The `break` statement is used to ensure that “fall through” doesn't occur.

1. On the Visual Studio Code **File** menu, select **Save**.

1. In the EXPLORER view, right-click **Starter**, and then select **Open in Integrated Terminal**.

    A TERMINAL panel should open below the code Editor area.

    There are several ways to open Visual Studio Code's integrated terminal. For example, the top menu provides access to the TERMINAL panel from both the **View** menu and the **Terminal** menu. You may also learn keyboard shortcuts that open the TERMINAL panel. Each method is acceptable.

1. Notice that the TERMINAL panel includes a command line prompt, and that the prompt shows the current folder path. For example:

    ```txt
    C:\Users\someuser\Desktop\GuidedProject\Starter>
    ```

    You can use the TERMINAL panel to run Command Line Interface (CLI) commands, such as `dotnet build` and `dotnet run`. The `dotnet build` command will compile your code and display error and warning messages related to your code syntax.

    > [!IMPORTANT]
    > You need to ensure that terminal command prompt is open to the root of your project workspace. In our case, the root of our project workspace is the Starter folder, where our Starter.csproj and Program.cs files are located. When we run commands in the terminal, the commands will try to perform actions using current folder location. If we try to run the `dotnet build` or `dotnet run` commands from a folder location that does not contain our files, the commands will generate error messages.

1. At the TERMINAL command prompt, to build your project code, enter the following command: `dotnet build`  

    After a couple seconds, you should see a message telling you that your build succeeded, and that you have 0 Warning(s) and 0 Error(s).

    ```txt
    Determining projects to restore...
    All projects are up-to-date for restore.
    Starter -> C:\Users\someuser\Desktop\GuidedProject\Starter\bin\Debug\net6.0\Starter.dll

    Build succeeded.
        0 Warning(s)
        0 Error(s)
    ```

1. If you see Error or Warning messages, you need to fix them before continuing.

    Error and Warning messages list the code line where the issue can be found. The following message is an example of a `Build FAILED` error message:

    `C:\Users\someuser\Desktop\GuidedProject\Starter\Program.cs(53,18): error CS1002: ; expected [C:\Users\someuser\Desktop\GuidedProject\Starter\Starter.csproj]`

    This message tells us the type of error that was detected and where to find it. In this case, the message tells us that our Program.cs file contains an error - `error CS1002: ; expected`. The `; expected` suggests that we forgot to include a `;` at the end of a statement. The `Program.cs(53,18)` portion of the message tells us that the error is located on code line 53, at a position 18 characters in from the left.

    A syntax error like this prevents our Build from succeeding (Build FAILED). Some Build messages provide a "Warning" instead of an "Error", which means there's something to be concerned with, but we can try running the program anyway (Build succeeded).

    Once you've fixed the issues and saved your updates, you can run the `dotnet build` command again. Continue until you have 0 Warning(s) and 0 Error(s).

    > [!NOTE]
    > If you have trouble resolving an issue on your own, you can examine the Program.cs code in the Final folder that's included as part of the download that you completed during Setup. The Program.cs code in the Final folder represents the conclusion of all exercises in this module, so it will include code that you have not created yet. It may look considerably different than the Program.cs code that you have developed at this point in the Guided project. However, you can try examining the Program.cs code in Final to help you isolate and fix an issue in your code if you need to. Try not to use the code in the Final folder as a guide if you can avoid it. Remember that we learn from our mistakes and that every developer spends time finding and fixing errors.

1. Close the Terminal panel.

## Create program menu loop

In this task, we'll build a `do` loop that surrounds the menu options and the code that reads the user's menu selection. This loop will ensure that the main menu is refreshed for the user after our code processes a user's menu selection. This loop will continue until the user chooses to exit the program. Let's get started.

1. In the Visual Studio Code Editor, at the top of the code that's used to display the menu options, locate the following Line Comment:

    ```c#
    // display the top-level menu options
    ```

1. Create a blank code line above the comment, and then enter the following code:

    ```c#
    do
    {

    ```

    By enclosing the program's menu options inside a `do` loop, we ensure that the user will see the menu options at least one time.

1. Scroll down to the bottom of the code file.

1. Create a blank code line below the code that pauses code execution, and then update the code as follows:

    ```c#
    // pause code execution
    readResult = Console.ReadLine();

    } while ();
    ```

    Notice that we've closed the code block for the `do` loop, and that we've begun the construction of our while statement.

1. To specify the Boolean expression that will be evaluated by the while statement, update the while statement as follows:

    ```c#
    while (menuSelection != "exit");
    ```

    This expression will ensure that our `do` loop iterates, displaying the menu and reading the user selection, until the user chooses to "exit" the application.

1. Notice that the code line indentation isn't what we expect to see inside the code block of our `do` loop.

1. To have Visual Studio Code "fix" the indentation of your code lines, right-click inside the code Editor, and then select **Format Document**.

    In addition to properly indenting code lines, the **Format Document** command will apply other code formatting rules. However, it doesn't fix syntax errors in your code, and it can have unexpected results if your code includes incomplete or malformed code blocks. The **Format Document** command can be helpful as long as you're careful.

    The keyboard shortcuts to invoke this command are:
    - On Windows Shift + Alt + F
    - On Mac Shift + Option + F
    - On Linux Ctrl + Shift + I

    This command can also be found using the Command Palette. To find the Format Document command from the Command Palette:

    - On the **View** menu, select **Command Palette**, and then enter **Format D** at the prompt.
    - The filtered list of commands will show **Format Document** as a selectable command

1. On the Visual Studio Code **File** menu, select **Save**.

1. Open the Integrated Terminal panel.

    You can open Terminal panel by right-clicking the **Starter** folder in the EXPLORER, and then selecting **Open in Integrated Terminal**.

1. At the Terminal command prompt, enter the `dotnet build` command to build your updated code.

    You should see the message reporting 0 Warning(s) and 0 Error(s)

1. Fix any Build errors or warnings that you see reported before continuing.

1. At the Terminal command prompt, enter the `dotnet run` command to run your updated code.

    Your application will start running.

1. Verify that the main menu options are displayed in the Terminal panel as expected.

    You should see the following displayed in the TERMINAL panel.

    ```txt
    Welcome to the Contoso PetFriends app. Your main menu options are:
    1. List all of our current pet information
    2. Add a new animal friend to the ourAnimals array
    3. Ensure animal ages and physical descriptions are complete
    4. Ensure animal nicknames and personality descriptions are complete
    5. Edit an animal's age
    6. Edit an animal's personality description
    7. Display all cats with a specified characteristic
    8. Display all dogs with a specified characteristic

    Enter your selection number (or type Exit to exit the program)
    ```

1. At the Terminal command prompt, to select menu option 1, enter **1**

    If your app is paused with the cursor located to the right of the 1, press Enter. To enter the value, you need to press the Enter key after typing the **1** character.

1. Verify that your code echoes back the menu selection that you entered.

    ```txt
    You selected menu option 1.
    Press the Enter key to continue
    ```

    If you don't see this message, ensure that you saved your code updates before running the `dotnet build` command. Save now if you didn't, and then rebuild your app before you try running it again.

1. At the Terminal command prompt, press the Enter key to continue,

    Pressing Enter enables your code to proceed past the `Console.ReadLine()` method that is located just before the `while` expression is evaluated at the end of the application.

1. To verify that your code continues to accept additional menu selections, try entering one or more of the other menu item numbers.

    If your code stopped running after you entered 1, make sure that you saved your code updates. If you didn't, save your code now and then run the program again.

    You may notice that you can enter any text or numeric value, or even a combination of letters and numbers. We'll address this issue when we develop the code that executes in response to the user's menu selections.

1. At the Terminal command prompt, to verify that our loop's exit criteria is being evaluated correctly, enter either **Exit** or **exit**.

    When you enter either "Exit" or "exit", and then press Enter after the code echoes your selection, the while expression should evaluate to `false` and the code execution should end.

    > [!IMPORTANT]
    > If code execution does not stop as expected when you enter "exit", you can press **Ctrl-C** in the Integrated Terminal to force execution to stop.

1. Close the Terminal panel.

## Write switch statement for menu selections

In this task, we'll write the code for a `switch` statement that branches our code execution based on the value assigned to `menuSelection`. We'll create a switch label that corresponds to each menu item number so that each menu item is managed separately. A `switch` is exactly what we need in order to satisfy the intended logic of our application. Let's get started.

1. In the Visual Studio Code Editor, locate the following `Console.WriteLine()` code line that's used to echo back our menu selection.

    ```c#
    Console.WriteLine($"You selected menu option {menuSelection}.");
    ```

1. To comment-out the `Console.WriteLine()` and `Console.ReadLine()` statements at the bottom of our code file and to begin the development of our `switch` statement, update your code as follows:

    ```c#
    //Console.WriteLine($"You selected menu option {menuSelection}.");
    //Console.WriteLine("Press the Enter key to continue");

    // pause code execution
    //readResult = Console.ReadLine();

    switch(menuSelection)
    {

    }

    ```

1. To add the first `case` pattern to our `switch` statement, update your `switch` statement code as follows:

    ```c#
    switch(menuSelection)
    {
        case "1":
            break;

    }
    ```

    You may have noticed that the case pattern used here looks slightly different from the case pattern used when building our sample data earlier in our application (`case 1:` versus `case "1":`). The difference is that we were checking integer values previously and we're checking string values now.
  
1. To create selection branches in your `switch-case` construct for each of the remaining menu selection numbers, add additional `case` options as follows:

    ```c#
    switch(menuSelection)
    {
        case "1":
            break;

        case "2":
            break;

        case "3":
            break;

        case "4":
            break;

        case "5":
            break;

        case "6":
            break;

        case "7":
            break;

        case "8":
            break;

    }
    ```

1. Notice that we can add the optional `default` case to the end of our selection list as follows:

    ```c#
    switch(menuSelection)
    {
        // case selections 1-7 have been removed to simplify this sample code 

        case "8":
            break;

        default:
            break;
    }
    ```

1. On the Visual Studio Code **File** menu, select **Save**.

1. Open the Integrated Terminal panel and then run the command to Build the program.

    Use the `dotnet build` command to build your updated code.

    You should see the message reporting 0 Warning(s) and 0 Error(s)

1. Fix any Build errors or warnings that you see reported before continuing.

1. Close the Terminal panel.

## Write placeholder code for each case of the switch statement

In this task, we'll update the code execution paths created by our `switch` statement. When we're done, each switch section will provide feedback to the user that acknowledges the user's menu selection. Providing feedback that acknowledges user input is especially important since we won't be able to complete the code for all menu options during this module. The feedback lets the user know that the code recognized their input, even if the application isn't able to process the request. Let's get started.

1. In the Visual Studio Code Editor, locate the code line containing the `case "1":` selection:

    ```c#
    switch (menuSelection)
    {
        case "1":
            break;

    ```

1. To provide a feedback message to the user between the `case "1":` and `break;` code lines, update your code as follows:

    ```c#
    switch (menuSelection)
    {
        case "1":
            // List all of our current pet information
            Console.WriteLine("this app feature is coming soon - please check back to see progress.");
            Console.WriteLine("Press the Enter key to continue.");
            readResult = Console.ReadLine();
            break;

    ```

1. Add the same feedback message for the `case "2":` selection as follows:

    ```c#
    switch (menuSelection)
    {
        case "1":
            // List all of our current pet information
            Console.WriteLine("this app feature is coming soon - please check back to see progress.");
            Console.WriteLine("Press the Enter key to continue.");
            readResult = Console.ReadLine();
            break;

        case "2":
            // List all of our current pet information
            Console.WriteLine("this app feature is coming soon - please check back to see progress.");
            Console.WriteLine("Press the Enter key to continue.");
            readResult = Console.ReadLine();
            break;

    ```

1. Update the Line Comment for the `case "2":` selection to reflect the second menu option as follows:

    ```c#
    case "2":
        // Add a new animal friend to the ourAnimals array
        Console.WriteLine("this app feature is coming soon - please check back to see progress.");
        Console.WriteLine("Press the Enter key to continue.");
        readResult = Console.ReadLine();
        break;

    ```

1. For the `case "3":` through `case "8":` selections, update your code with a Line Comment that reflects the associated menu item text.

    For example, add `// Ensure animal ages and physical descriptions are complete` below `case "3":`

    You can copy the menu item text from the code lines that display the menu options.

    > [!NOTE]
    > You can use the "Format Document" command to clean up your formatting either as you go or after you have finished entering the Line Comments and code lines in the upcoming steps. This may speed up your work and give you more time to focus on the code that you are entering rather than how it looks.

1. For the `case "3":` and `case "4":` selections, add the following feedback message and ReadLine() below the Line Comment: 

    ```c#
    Console.WriteLine("Challenge Project - please check back soon to see progress.");
    Console.WriteLine("Press the Enter key to continue.");
    readResult = Console.ReadLine();
    ```

1. For the remaining `case` selections, update your code with the following feedback message and ReadLine():

    ```c#
    Console.WriteLine("UNDER CONSTRUCTION - please check back next month to see progress.");
    Console.WriteLine("Press the Enter key to continue.");
    readResult = Console.ReadLine();
    ```

    > [!NOTE]
    > If you added the optional `default` case to your selection list, don't add the feedback message to that case.

1. On the Visual Studio Code **File** menu, select **Save**.

    Recall that Visual Studio Code will format your code if you right-click inside the code Editor and then select **Format Document** from the context menu.

1. Open the Integrated Terminal panel and then run the command to Build the program.

    Use the `dotnet build` command to build your updated code.

1. Fix any Build errors or warnings that you see reported before continuing.

## Check your work

In this task, we'll run our application from the Integrated Terminal and verify that our `switch` statement is branching our code as intended and that the expected feedback messages are being displayed for each menu selection. We'll also retest the exit criteria of our main menu loop. Let's get started.

1. If necessary, open Visual Studio Code's Integrated Terminal panel.

1. At the Terminal command prompt, enter **dotnet run**

1. At the Terminal command prompt, to select the first menu option, enter **1**

1. Verify that the expected "coming soon" message is displayed.

1. Repeat the previous step, entering each of the other menu option numbers to verify that the expected message is displayed in each case.

1. At the Terminal command prompt, enter either **Exit** or **exit** to verify that our exit criteria is still being evaluated correctly.

    > [!IMPORTANT]
    > If code execution does not stop as expected, you can press **Ctrl-C** in the Integrated Terminal to force execution to stop.  

1. Close the Terminal panel.
