TODO: Prepare

Set expectations in the Prepare unit. Describe what they'll build and walk them through any required setup.

The first level-2 heading (H2) is "Project specification" and gives a specification for the project they'll build. Don't include any details about how they'll create it, that's part of the challenge.
The second H2 is "Setup" and walks them through the setup of all needed tools, installations, accounts, etc.
The second H2 is optional. If the project doesn't require any "Setup", remove the "Project overview" heading to avoid a page with a title followed by a single H2.

---------------------------------------------------------------------------------------------------------------------------------------------------------------

You'll be using Visual Studio Code to develop portions of a C# console application. You will be writing code that evaluates boolean expressions, implements various selection and iteration statements (branching and looping structures), and declares variables within code blocks at the appropriate scoping level for the app. Here, we'll discuss the overall goals of the project and how you'll build and test your application. We'll also cover how to set up your development environment, including a "Starter" code project.

## Project specification

The Starter code project for this module includes a Program.cs file with the following code features:

- the code declares variables used to collect and process pet data and menu item selections
- the code declares the ourAnimals array that includes the following information for each animal in the array:

    - pet ID #
    - pet species (cat or dog)
    - pet age (years)
    - a description of the pet's physical appearance
    - a description of the pet's personality
    - the pet's nickname

- the code uses a for loop around a select-case construct to populate elements of the ourAnimals array  
- the code includes a loop around a main menu that terminates when the user enters "exit". The main menu includes:

    1. List all of our current pet information
    1. Assign values to the ourAnimals array fields
    1. Ensure animal ages and physical descriptions are complete
    1. Ensure animal nicknames and personality descriptions are complete
    1. Edit an animal’s age
    1. Edit an animal’s personality description
    1. Display all cats with a specified characteristic
    1. Display all dogs with a specified characteristic

    Enter menu item selection or type "Exit" to exit the program

- the code reads the user's menu item selection and uses a switch statement to branch the code for each menu item number
- the code includes implementation for menu options 1 and 2.
- the code displays an "under construction" message for menu options 3-8.  

Your goal in this challenge is to create the app features aligned with menu options 3 and 4.

> [!NOTE]
> New animals must be added to the ourAnimals array when the y arrive. However, an animal's age and some physical characteristics for a pet may be unknown until after a veterinarian's examination. In addition, an animal's nickname and personality may be unknown when a pet first arrives. The new features that you have volunteered to develop will be used to ensure that we have a completed dataset for each animal in the ourAnimals array.

To complete the feature that ensures animal ages and physical descriptions are complete, your code will need to:

    - assign a valid numeric value to petAge for any animal that has been assigned data in the ourAnimals array but has not been assigned an age
    - assign a valid string to petPhysicalDescription for any animal that has been assigned data in the ourAnimals array but has not been assigned a physical description
    - a valid physical description cannot be null and cannot have zero characters, any further requirement is up to you

To complete the feature that ensures animal nickname and personality descriptions are complete, your code will need to:

    - assign a valid string to petNickname for any animal that has been assigned data in the ourAnimals array but has not been assigned a nickname
    - assign a valid string to petPersonalityDescription for any animal that has been assigned data in the ourAnimals array but has not been assigned a personality description
    - a valid nickname or personality description cannot be null and cannot have zero characters, any further requirement is up to you 

## Setup

Use the following steps to prepare for the Guided project exercises.

1. Notice that the GitHub repo for this Module includes the following folders:

    The **M07-challenge-project** folder contains the following folders:

    ```Output
    includes
    LabFiles
    ```

    The **includes** folder contain the training materials.

    The **LabFiles** folder contains console applications related to this Challenge project module. The **Starter** folder contains the code that you will start with for this coding project. The **Final** folder contains the solution code. You should not need the solution code to finish the Guided project.

1. Use Visual Studio Code to create a new console app.

1. Open the **LabFiles** folder, and then open the **Starter** folder.

    The **Starter** folder contains a Program.cs file.

1. Copy the contents of the Program.cs file to the clipboard.

1. Switch to the new console application that you created, and then open the Program.cs file.

    The default Program.cs file is a Hello World app.

1. Replace the contents of your new Program.cs file with the code that you copied to the clipboard.

You are now ready to begin the Challenge project exercises. Good luck!
