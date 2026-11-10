Unit Title: Exercise - Ensure that petAge and petPhysicalDescription contain valid information
-----------------------------------------------------------------------------------------------------------------------------------------------

The Contoso Pets app is used to help find new homes for abandoned pets. Your goal in this challenge is to develop the app features used to ensure that we have a completed dataset for each animal in the ourAnimals array.

## Specification

You need to develop a feature that ensures animal nicknames and personality descriptions are complete.

This feature must:

    - be enabled inside the appropriate application branch (must not overwrite the code in the code branch for menu option 2)
    - skip over any animal in the ourAnimals array when the value of pet ID is set to the value default value
    - display the pet ID value and prompt the user for an updated data value if ourAnimals array data is missing or incomplete
    - ensure that a valid numeric value is assigned to animalAge for all animals in the ourAnimals array that have assigned data
    - ensure that a valid string is assigned to animalPhysicalDescription for all animals in the ourAnimals array that have assigned data
    - enforce the following validation rules for petNickname and petPersonalityDescription:

        - values cannot be null
        - values cannot have zero characters
        - any further restriction is up to the developer 

    - inform the application user when all data requirements are met, pausing the application to ensure the message can be seen and responded to

## Check your work

To validate that your code satisfies the specified requirements, complete the following steps:

1. Use Visual Studio Code to build and run your app.

1. At the Terminal command prompt, enter **4**

1. Verify that the Terminal panel updates with a message similar to the following:

    ```Output
    Enter a nickname for ID #: c4

    ```

1. At the Terminal command prompt, press the Enter key (without typing any characters)

1. Verify that your code repeats the prompt requesting a value for the age of the pet.

    The Terminal panel should update to display something similar to the following:

    ```Output
    Enter a nickname for ID #: c4

    Enter a nickname for ID #: c4

    ```

1. At the Terminal command prompt, enter **snowflake**

1. Verify that your code accepts **snowflake** as a valid entry and that the Terminal panel displays a message similar to the following:

    ```Output
    Enter a personality description for ID #: c4 (likes or dislikes, tricks, energy level)
    ```

1. At the Terminal command prompt, press the Enter key (without typing any characters)

1. Verify that your code repeats the prompt requesting a value for the physical description of the pet.

    The Terminal panel should update to display something similar to the following:

    ```Output
    Enter a personality description for ID #: c4 (likes or dislikes, tricks, energy level)
        
    Enter a personality description for ID #: c4 (likes or dislikes, tricks, energy level)

    ```

1. At the Terminal command prompt, enter **loves to curl up in a warm spot**

1. Verify that your code accepts **loves to curl up in a warm spot** as a valid entry and that the Terminal panel displays a message similar to the following:

    ```Output
    Nickname and personality description fields are complete for all of our friends. 
    Press the Enter key to continue
    ```

1. If you specified further restrictions for valid entries, run the appropriate test cases to verify your work.

Congratulations if you succeeded in this challenge!
