---
title: Exercise - Add suggestedDonation data
durationInMinutes: 10
---

In this step of our development process, we'll update the code provided in the Starter project folder, adding features for "suggested donation" to our application. The starter project.cs file should be open in VSCode. Return to earlier prepare unit if you need instructions for getting started.

The detailed tasks that we'll complete during this exercise are:

1. Add data: create data for `suggestedDonation`
    1. Declare `suggestedDonation` string.
    1. Expand the `ourAnimals` array to account for the addition of the `suggestedDonation` data for each animal.
    1. Populate sample data: add `suggestedDonation` amounts.
1. Clean up for `suggestedDonation`: review and update usage of `ourAnimals` array to account for addition of `suggestedDonation`.
1. Verification test: perform verification tests for the code that you've developed in this exercise.

## Create `suggestedDonation` data

1. Notice the code under comment #1 that declares data populating the `ourAnimals` array. This is where you need to declare the `suggestedDonations` string.

    ```csharp
    // #1 the ourAnimals array will store the following: 
    string animalSpecies = "";
    string animalID = "";
    string animalAge = "";
    string animalPhysicalDescription = "";
    string animalPersonalityDescription = "";
    string animalNickname = "";
    ```

    Below the declaration of `animalNickname`, add the declaration for the `suggestedDonations` adding the following code:

    ```csharp
    string suggestedDonation = "";
    ```

1. Enable `ourAnimals` array to contain `suggestedDonation`
    - Locate comment # 3 to update the creation of the `ourAnimals` array.
    - Update `ourAnimals` array to hold 7 "columns" of data for each animal instead of 6 as follows:

    `string[,] ourAnimals = new string[maxPets, `**`7`**`];`

1. Add `suggestedDonation` amounts to the sample data. Locate comment #4 and inside the switch statement insert a `suggestedDonation` value above the `break` statement for `case 0;` through `case 3:` with the following values:
    
    - Case 0: `suggestedDonation = "85.00";`
    - Case 1: `suggestedDonation = "49.99";`
    - Case 2: `suggestedDonation = "40.00";`
    - Case 3: `suggestedDonation = "";`

1. Locate the code below where the array is populated with the pet data from case statements (it's above comment # 5):

    ```csharp
        ourAnimals[i, 0] = "ID #: " + animalID;
        ourAnimals[i, 1] = "Species: " + animalSpecies;
        ourAnimals[i, 2] = "Age: " + animalAge;
        ourAnimals[i, 3] = "Nickname: " + animalNickname;
        ourAnimals[i, 4] = "Physical description: " + animalPhysicalDescription;
        ourAnimals[i, 5] = "Personality: " + animalPersonalityDescription;
    ```

1. Notice that `suggestedDonation` data isn't included as part of the sample data starter code for populating the array. Although it would make sense to populate the array with a statement like:
    
    `ourAnimals[i, 6] = "Suggested Donation: "  + suggestedDonation;`, that could leave you with issues casting a string to a number.

    `suggestedDonation` is a numeric value that is stored as a string. In the future you may want to validate `suggestedDonation` represents a decimal, and that you can convert it to a decimal so it is available to use for billing calculations. Therefore you will add `TryParse` validation to the end of the code shown above populating the array.

    **Add the following:**

    ```csharp
    if (!decimal.TryParse(suggestedDonation, out decimalDonation)){
    decimalDonation = 45.00m;
    }
    ```

    Notice if `suggestedDonation` cannot be cast as a decimal the code assigns a default value `decimalDonation = 45.00m;`. If the cast is successful, the `TryParse` populates `decimalDonation`. Either way, `decimalDonation` will represent a proper decimal.

    Don't forget, you need to declare `decimalDonation` you just a added to the code.

    Following the comment #2 code, declare `decimalDonation`:

    ```csharp
    decimal decimalDonation = 0.00m;
    ```

1. Finally, you are ready to populate `suggestedDonation` data for each pet, but using the `decimalDonation` version that has been cast to a decimal and using string interpolation and currency formatting.
In the array populating code, immediately after the `TryParse` you completed, **add the following code**:

    ```csharp
    ourAnimals[i, 6] = $"Suggested Donation: {decimalDonation:C2}";
    ```

Notice that by using the code `{decimalDonation:C2}` the suggested donation, from `decimalDonation`, will display with the local currency symbol and 2 decimal places as directed by the currency formatting `:C2`.

## Review and update where `ourAnimals` array should be used

The addition of the `suggestedDonation` data created need for further updates. The menu option `"1. List all of our current pet information"` is missing the added data.

1. Notice the code under comment #5, for the menu loop within `case 1.

    The inner loop "`for (int j = 0; j < `**`6`**`; j++)`" that prints the pet attributes needs to account for  `suggestedDonation` data being added.

2. Update the inner loop code exit condition to be increased by "1", so it becomes `j < `**`7`**. Your code should now match the code below:

    ```csharp
    case "1":
    // list all pet info
    for (int i = 0; i < maxPets; i++)
    {
        if (ourAnimals[i, 0] != "ID #: ")
        {
            Console.WriteLine();
            for (int j = 0; j < 7; j++) // increased exit condition
            {
                Console.WriteLine(ourAnimals[i, j].ToString());
            }
        }
    }
    ```

## Test cases

With several code additions in place, you need to confirm your code works as expected. The 2 big test areas are:

1. The code complies without errors.
1. Selecting menu option 1 all pet information displays:
    - Output includes all of sample pet information, including: ID, species, age, nickname, physical description, and personality description.
    - For each pet, the suggested donation displays with a currency symbol and with 2 decimal places of precision.

**Build and run to test the code.** Use these steps each time you need to test your code in the following exercises.

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

    > [!NOTE]
    > Use the above `dotnet build` and `dotnet run` steps each time you need to test your code in the exercises that follow in this module.

1. If you see Error or Warning messages, you need to fix them before continuing.

    Error and Warning messages list the code line where the issue can be found. The following message is an example of a `Build FAILED` error message:

    `C:\Users\someuser\Desktop\GuidedProject\Starter\Program.cs(53,18): error CS1002: ; expected [C:\Users\someuser\Desktop\GuidedProject\Starter\Starter.csproj]`

    This message tells us the type of error that was detected and where to find it. In this case, the message tells us that our Program.cs file contains an error - `error CS1002: ; expected`. The `; expected` suggests that we forgot to include a `;` at the end of a statement. The `Program.cs(53,18)` portion of the message tells us that the error is located on code line 53, at a position 18 characters in from the left.

    A syntax error like this prevents our Build from succeeding (Build FAILED). Some Build messages provide a "Warning" instead of an "Error", which means there's something to be concerned with, but we can try running the program anyway (Build succeeded).

    Once you've fixed the issues and saved your updates, you can run the `dotnet build` command again. Continue until you have 0 Warning(s) and 0 Error(s).

    > [!NOTE]
    > If you have trouble resolving an issue on your own, you can examine the Program.cs code in the Final folder that's included as part of the download that you completed during Setup. The Program.cs code in the Final folder represents the conclusion of all exercises in this module, so it will include code that you have not created yet. It may look considerably different than the Program.cs code that you have developed at this point in the Guided project. However, you can try examining the Program.cs code in Final to help you isolate and fix an issue in your code if you need to. Try not to use the code in the Final folder as a guide if you can avoid it. Remember that we learn from our mistakes and that every developer spends time finding and fixing errors.

1. Test the updated console app, at the TERMINAL command prompt build & run your project code with one command by entering: `dotnet run`. When the code runs two menu items are displayed.
    - Enter "`1`" to test the "display all pets" output
    - Enter "`2`" to test the placeholder message "under construction" message

    The output for menu item #1 should closely match the following:

    ```output
    ID #: d1
    Species: dog
    Age: 2
    Nickname: lola
    Physical description: medium sized cream colored female golden retriever weighing about 45 pounds. housebroken.
    Personality: loves to have her belly rubbed and likes to chase her tail. gives lots of kisses.
    Suggested Donation: $85.00
    
    ID #: d2
    Species: dog
    Age: 9
    Nickname: gus
    Physical description: large reddish-brown male golden retriever weighing about 85 pounds. housebroken.
    Personality: loves to have his ears rubbed when he greets you at the door, or at any time! loves to lean-in and give doggy hugs.
    Suggested Donation: $49.99
    
    ID #: c3
    Species: cat
    Age: 1
    Nickname: snow
    Physical description: small white female weighing about 8 pounds. litter box trained.
    Personality: friendly
    Suggested Donation: $40.00
    
    ID #: c4
    Species: cat
    Age:
    Nickname: lion
    Physical description:
    Personality:
    Suggested Donation: $45.00
    ```

    If everything worked as expected, congratulations! Otherwise, look for the error by checking code instruction steps involved.  If needed, start over with a new starter Project.cs file and if you still have issues check the solution folder code for this exercise.

1. Type `exit`, at the app menu, to end the program and then close the terminal panel.
