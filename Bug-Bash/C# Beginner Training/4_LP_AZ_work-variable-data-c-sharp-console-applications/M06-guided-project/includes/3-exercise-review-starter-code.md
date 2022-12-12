---
title: Exercise - Review starter code
durationInMinutes: 6
---

In this first step of our development process, we'll review the code provided in the Starter project folder.

## Review the contents of the Program.cs file

In this task, we'll review the code that's provided as a Starter project for this module. The Program.cs file contains a preliminary version of the application that we'll be working on. The code includes features to generate and display the sample data for the application, and it displays a list of menu options that define the main features of our application. Let's take a look.

1. Ensure that you have the **GuidedProject** folder open in Visual Studio Code.

    The **Prepare** unit (the previous unit in this module) includes a Setup section that describes the process for downloading the initial starting point for our Guided project and opening the folder Visual Studio Code. If necessary, go back and follow the Setup instructions.

1. In the **EXPLORER** view, expand the **Starter** folder, then select **Program.cs**.

    When you select the Program.cs file, the file contents will open in the main Editor area to the right of the EXPLORER.

    If the EXPLORER view isn't open, you can select/open the EXPLORER view from the Activity Bar on the far left side of VS Code. EXPLORER is the topmost icon on the Activity Bar.

1. Take a few minutes to review the initial variable declarations at the top of the Program.cs file.

    ``` c#
    // #1 the ourAnimals array will store the following: 
    string animalSpecies = "";
    string animalID = "";
    string animalAge = "";
    string animalPhysicalDescription = "";
    string animalPersonalityDescription = "";
    string animalNickname = "";

    // #2 variables that support data entry
    int maxPets = 8;
    string? readResult;
    string menuSelection = "";

    // #3 array used to store runtime data, there is no persisted data
    string[,] ourAnimals = new string[maxPets, 6];
    ```

    First, we see a comment (comment #1) followed by a list of variables. These variables, `animalSpecies` through `animalNickname`, will be used to hold the values of the pet characteristics within a multidimensional string array named `ourAnimals`. Each of these variables is initialized to contain a zero length string `""`. The `ourAnimals` array is declared a little further down in the code (we'll get to it soon).

    The next group of variables (under comment #2) is a mix of `string` and `int` variables that will be used help generate sample data, read user input, and establish exit criteria for our main program loop. Notice the code line `string? readResult;`. The `?` character is used to transform a normally non-nullable variable type (int, string, bool,...) with support for the nullable type. When reading user entered values with the `Console.ReadLine()` method, it's best to enable a nullable type string using `string?`.

    The final variable (under comment #3) is our two-dimensional string array named `ourAnimals`.  The number of rows is defined by maxPets, which has been initialized to 8. The number of characteristics that we're storing initially is six. This matches the number of string variables that we examined above, but will need to expand as we will be adding a field for `suggestedDonation`.  

1. Scroll down the Program.cs file to examine the `for` loop that contains an `switch` selection construct within its code block. The code below is a shortened version to save space.

    ```csharp
    // #4 create sample data ourAnimals array entries
    for (int i = 0; i < maxPets; i++)
    {
        switch (i)
        {
            case 0:
                animalSpecies = "dog";
                animalID = "d1";
                animalAge = "2";
                animalPhysicalDescription = "medium sized cream colored female golden retriever weighing about 45 pounds. housebroken.";
                animalPersonalityDescription = "loves to have her belly rubbed and likes to chase her tail. gives lots of kisses.";
                animalNickname = "lola";
                break;
    
            case 1:
                animalSpecies = "dog";
                animalID = "d2";
                animalAge = "9";
                animalPhysicalDescription = "large reddish-brown male golden retriever weighing about 85 pounds. housebroken.";
                animalPersonalityDescription = "loves to have his ears rubbed when he greets you at the door, or at any time! loves to lean-in and give doggy hugs.";
                animalNickname = "gus";
                break;
            
            // case 2: deleted for brevity
            // case 3: deleted for brevity
            
            default:
                animalSpecies = "";
                animalID = "";
                animalAge = "";
                animalPhysicalDescription = "";
                animalPersonalityDescription = "";
                animalNickname = "";
                break;
        }
        ourAnimals[i, 0] = "ID #: " + animalID;
        ourAnimals[i, 1] = "Species: " + animalSpecies;
        ourAnimals[i, 2] = "Age: " + animalAge;
        ourAnimals[i, 3] = "Nickname: " + animalNickname;
        ourAnimals[i, 4] = "Physical description: " + animalPhysicalDescription;
        ourAnimals[i, 5] = "Personality: " + animalPersonalityDescription;
    }
    ```

1. Notice that the `for` loop uses the `maxPets` variable to establish an upper bound on the number of iterations below comment # 4. Also notice that the `switch` construct selectively branches our code so that we can define different pet characteristics for the pets in our sample data set.

    The `switch` construct is used to define different values for the first four iterations of the `for` loop. After that fourth iteration (or after the second iteration for the shortened sample above), all characteristics are assigned an empty, or zero-length, string.

    The values of the animal characteristic variables are assigned to the ourAnimals array at the bottom of the `for` loop.
    
1. Scroll to the bottom of the code file in VSCode, and then examine the code that's used to display the menu options and read the user selection. There are only two options since this is a limited version of the application our teammates provided us with only the capabilities needed for running and testing features we will prototype.
    
    ```C#
    // #5 display the top-level menu options
    do
    {
        // NOTE: the Console.Clear method is throwing an exception in debug sessions
        Console.Clear();
    
        Console.WriteLine("Welcome to the Contoso PetFriends app. Your main menu options are:");
        Console.WriteLine(" 1. List all of our current pet information");
        Console.WriteLine(" 2. Display all dogs with a specified characteristic");
        Console.WriteLine();
        Console.WriteLine("Enter your selection number (or type Exit to exit the program)");
    
        readResult = Console.ReadLine();
        if (readResult != null)
        {
            menuSelection = readResult.ToLower();
        }
    
        // use switch-case to process the selected menu option
        switch (menuSelection)
        {
            case "1":
                // list all pet info
                for (int i = 0; i < maxPets; i++)
                {
                    if (ourAnimals[i, 0] != "ID #: ")
                    {
                        Console.WriteLine();
                        for (int j = 0; j < 6; j++)
                        {
                            Console.WriteLine(ourAnimals[i, j].ToString());
                        }
                    }
                }
                Console.WriteLine("\n\rPress the Enter key to continue");
                readResult = Console.ReadLine();
                break;
    
            case "2":
                // Display all dogs with a specified characteristic");
                Console.WriteLine("\nUNDER CONSTRUCTION - please check back next month to see progress.");
                Console.WriteLine("Press the Enter key to continue.");
                readResult = Console.ReadLine();
                break;
    
            default:
                break;
        }
    
    } while (menuSelection != "exit");
    ```

1. Notice that we have again assign the value returned by the `Console.ReadLine()` method to the nullable string `readResult` to avoid the code compiler generating a warning when we build our project.

    The final lines of our Program.cs file echo the menu option selection, and then pause execution until the Enter key is pressed.

1. Test the starter code console app, at the TERMINAL command prompt build & run your project code with one command by entering: `dotnet run`. When the code runs two menu items are displayed.
    - Enter "`1`" to test the "display all pets" output
    - Enter "`2`" to test the placeholder message "under construction" message

1. Type `exit`, at the app menu, to end the program and then close the terminal panel.
