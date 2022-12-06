Unit Title: Exercise - Ensure that petAge and petPhysicalDescription contain valid information
-----------------------------------------------------------------------------------------------------------------------------------------------

The Contoso Pets app is used to help find new homes for abandoned pets. Your goal in this challenge is to develop the app features used to ensure that we have a completed dataset for each animal in the ourAnimals array.

## Specification

In this first challenge exercise, you need to develop a feature that ensures animal ages and physical descriptions are complete.

This feature must:

- be enabled inside the appropriate application branch (must not overwrite the code in the code branch for menu option 2)
- skip over any animal in the ourAnimals array when the value of pet ID is set to the default value
- display the pet ID value and prompt the user for an updated data value if ourAnimals array data is missing or incomplete
- ensure that a valid numeric value is assigned to animalAge for all animals in the ourAnimals array that have assigned data
- ensure that a valid string is assigned to animalPhysicalDescription for all animals in the ourAnimals array that have assigned data
- enforce the following validation rules for animalAge

    - it must be possible to convert the value entered to numeric data type

- enforce the following validation rules for animalPhysicalDescription:

    - values cannot be null
    - values cannot have zero characters
    - any further restriction is up to the developer 

- inform the application user when all data requirements are met, pausing the application to ensure the message can be seen and responded to

## Check your work

To validate that your code satisfies the specified requirements, complete the following steps:

1. Use Visual Studio Code to build and run your app.

> [!NOTE]
> You can exit the verification test before completing all of the verification steps if see a result that does not satisfy the specification requirements. To force an exit from the running program, in the Terminal panel, press **Ctrl-C**. After exiting the running app, complete the edits that you believe will address the issue you are working on, save your updates to the Program.cs file, and then re-build and run your code.

1. At the Terminal command prompt, enter **3**

1. Verify that the Terminal panel updates with a message similar to the following:

    ```Output
    Enter an age for ID #: c4

    ```

1. At the Terminal command prompt, enter **one**

1. Verify that your code repeats the prompt requesting a value for the age of the pet.

    The Terminal panel should update to show the repeated prompt. The display should be similar to the following:

    ```Output
    Enter an age for ID #: c4
    one
    Enter an age for ID #: c4

    ```

1. At the Terminal command prompt, enter **1**

1. Verify that your code accepts **1** as a valid numeric entry and that the Terminal panel displays a message similar to the following:

    ```Output
    Enter a physical description for ID #: c4 (size, color, breed, gender, weight, housebroken)
    ```

1. At the Terminal command prompt, press the Enter key (without typing any characters)

1. Verify that your code repeats the prompt requesting a value for the physical description of the pet.

    The Terminal panel should update to show the repeated prompt. The display should be similar to the following:

    ```Output
    Enter a physical description for ID #: c4 (size, color, gender, weight, housebroken)
        
    Enter a physical description for ID #: c4 (size, color, gender, weight, housebroken)

    ```

1. At the Terminal command prompt, enter **small white Siamese cat weighing about 8 pounds. litter box trained.**

1. Verify that your code accepts **small white Siamese cat weighing about 8 pounds. litter box trained.** as a valid entry and that the Terminal panel displays a message similar to the following:

    ```Output
    Age and physical description fields are complete for all of our friends. 
    Press the Enter key to continue
    ```

1. If you specified further restrictions for valid entries, run the appropriate test cases to verify your work.

> [!NOTE]
> If your code meets the requirements you should be able to complete each step in order and see the expected results in a single test pass. If you added additional restrictions, you may need to exit the application and then run a separate test pass to complete your verification.

Congratulations if you succeeded in this challenge!
