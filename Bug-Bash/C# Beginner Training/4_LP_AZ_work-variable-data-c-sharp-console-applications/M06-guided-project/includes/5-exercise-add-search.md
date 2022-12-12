---
title: Exercise - Add dog search
durationInMinutes: 8
---

In this exercise you'll add the feature "Display all dogs with a specified characteristic" (menu item #2) to the application. The exercise uses the solution project from the previous exercise that added `suggestedDonation` data.

> [!NOTE]
> This is a "minimal viable product" (MVP) feature. A MVP feature is intended to be a simple working prototype of a feature that enables quick and easy delivery. A MVP is not usually a final product, it is intended to help you work through an idea, test it, and gather further requirements.

The search feature prompts the user for a single search input term (or phrase) that describes a characteristic desired in a pet to adopt. Then, all of the descriptions for adoptable dogs are searched for exact matches of the user input and information about the dogs that match are output to the console.  If no matches are identified, then a message *"None of our dogs are a match"* is displayed along with the search term used.

The tasks that you'll complete during this exercise are:

1. Gather user input for the pet characteristic search term
1. Loop through the animals array and identify "dogs"
1. For each dog, search the pet description for a term match
1. Display the dogs that have a term match

 In VSCode, open the completed Project.cs file from the pervious exercise that added the donation information to get started.

## Gather user input for the pet characteristic search

1. Review the menu switch statement below comment #5 in the Project.cs code. You will discover the code that displays the *"UNDER CONSTRUCTION"* message.
1. Delete the code between `case "2":` and the `break;` statement so the code matches the sample below:

    ```csharp
    case "2":
        // Display all dogs with a specified characteristic

        break; 
    ```

1. Add code to gather user input for a`dogCharacteristic` string. Gather the input requires a `while` loop that continues to prompt the user until they submit an input. The loop instructs the user to *"Enter one desired dog characteristics to search for"*. Entering an empty string will repeat the loop. Place the following code below `case "2:` just above the `break;` statement as shown:

    ```csharp
    case "2":
        // Display all dogs with a specified characteristic
        string dogCharacteristic = "";

        while (dogCharacteristic == "")
        {
            // have the user enter physical characteristics to search for
            Console.WriteLine($"\nEnter one desired dog characteristics to search for");
            readResult = Console.ReadLine();
            if (readResult != null)
            {
                dogCharacteristic = readResult.ToLower().Trim();
            }
        } 
    ```

    Review the added code. The main features of the `case "2":` code include:

    - The code starts with a string declaration `string dogCharacteristic = "";` that is scoped to `case "2":`. You  will not be able to utilize `dogCharacteristic` anywhere outside of the case statement code.
    - After `Console.ReadLine()` gathers user input as `dogCharacteristic` it ensures value is not null, and sets the string to lowercase and trims the surrounding spaces.
    - If `dogCharacteristic` has a null value, then the loop repeats gathering input.

1. Test the code so far.

    - Compile by using `dotnet build` (you can refer to the steps in the previous exercise) and fix any errors.
    - Test the search term input functionality of the app by using `dotnet run`.
        - Select Menu Option "2"
        - Press **"Enter"** without entering data at the *"Enter one desired dog characteristics to search for"* prompt to test the "TryParse". The program should return to the menu without error.
        - Return to Menu Option "2" and test by entering *"golden"*. The program should return to the menu without error.
        - Exit the program and close the terminal.

## Identify which animals are dogs

Now you add a feature to search with the user input `dogCharacteristic` within the dog descriptions following the pervious code under `case "2"`.

1. You will loop though each animal and search when you find a dog.
    Immediately after the the user input code, but still within `case "2"`, just above the `break;`, add the following code:

    ```csharp
    // #6 loop through the ourAnimals array to search for matching animals
    for (int i = 0; i < maxPets; i++)
    {
        if (ourAnimals[i, 1].Contains("dog"))
        {
            // #7 Search combined descriptions and report results
        }
    }
    ```

    Examine the loop above. It filters using the `ourAnimals[i, `**`1`**`]` code, animal data where `animalSpecies` data is stored. If it contains *"dog"* then the code moves into the brackets of the if statement where the search of the combined descriptions can occur.

1. Test the code so far compiles.

    - Compile by using `dotnet build` and fix any errors.

## Search the descriptions of dogs and display the match results

The previous code ensures that we will search only dog descriptions. Now you need to search the dog descriptions and output information about matches.

While thinking about the descriptions, you realize there are two descriptions `animalPhysicalDescription` and `animalPersonalityDescription;`. After consulting with your team, it is decided that a combined description is appropriate for the search.

    > [!NOTE]
    > Some developers refer to the addition of requirements during development as "scope creep." Although combining the descriptions is not a lot of work, it still adds time and complexity. For this reason, you should let the team know that added requirements will likely delay the completion of the project.

1.  You need to combine the the dog descriptions to make it easier to search. This requires declaring a string, `dogDescription` to hold the combined data that originated from `animalPhysicalDescription` and `animalPersonalityDescription;`. Declare `dogDescription` above comment #6 with the following code:

    ```csharp
    string dogDescription = "";
    ```

1. Using the `dogDescription` string declared we need to populate it with the two descriptions for each animal.  Add the following code below comment # 7:

    ```csharp
    dogDescription = ourAnimals[i, 4] + "\n" + ourAnimals[i, 5];
    ```

1. Now you will add the search for `dogCharacteristic` in the combined data of `dogDescription`. You will need to add an `if` statement to determine if we have a match for each search.

    Update the code below comment #7, after `dogDescription = ourAnimals[i, 4] + "\n" + ourAnimals[i, 5];` with the following code:

    ```csharp
                            if (dogDescription.Contains(dogCharacteristic))
                            {
                                Console.WriteLine($"\nOur dog {ourAnimals[i, 3]} is a match!");
                                Console.WriteLine(dogDescription);
                            }
    ```

    Examining the code above, when the `if` statement finds a match for `dogCharacteristic` in `dogDescription a message about the dog match and description is output to the console. You still need to account for a "no matches found" message.

1. To track when no matches are found, declare a Boolean tracking variable `bool noMatchesDog = true;`. When you find a match you can use `noMatchesDog = false;`. 

    To create the default `noMatchesDog = false` add the following code above comment #6:

    ```csharp
    bool noMatchesDog = true;
    ```

    Now "flip" the `noMatchesDog` from `false` to `true`. In the brackets of the `if (dogDescription.Contains(dogCharacteristic))` statement, add the following code:

    ```csharp
    noMatchesDog = false;
    ```

1. Finally, you need to create code that decides if the "no matches found" message should be written to the console. Within `case "2"` dog search, just above the `break;`, add the following code :

    ```csharp
    if (noMatchesDog)
    {
        Console.WriteLine("None of our dogs are a match found for: " + dogCharacteristic);
    }
    
    Console.WriteLine("\n\rPress the Enter key to continue");
    readResult = Console.ReadLine();
    ```

1. That's the the final code for this exercise! You can review the `case "2"` code below to see how you did. Remember there was also code added outside of `case "2"` for 

## Test cases

With several code additions in place, you need to confirm your code works as expected. The 2 big test areas are:

1. Compile your project code in the terminal using `dotnet build`.  

1. Test the updated console app. Run your project code in the terminal with `dotnet run`. When the code runs two menu items are displayed.
    - Enter "`2`" to test the Dog Search repeatedly by:
        - Entering nothing as input to test the `TryParse` to prevent a null error
        - Entering "scuba" as input to test the "match not found"
        - Entering "golden" to get 2 matches
        - Entering "medium" to get 1 match

    If everything worked as expected in both steps, congratulations! Otherwise, look for the errors by checking the exercise steps and follow the troubleshooting steps using the instructions provide in the previous exercise.  If needed, start over or check the solution folder code for this exercise.

1. Type `exit`, at the app menu, to end the program and then close the terminal panel.
