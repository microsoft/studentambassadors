Instructions for a Prepare unit: Set expectations in the Prepare unit. Describe what they'll build and walk them through any required setup.
- The first level-2 heading (H2) is "Project overview" and describes the project and how they'll build it at a high level.
- The second H2 is "Setup" and walks them through the setup of all needed tools, installations, accounts, etc.




TODO: This Guided project needs to be split into 2 separate Guide project modules. Split this project after the second Exercise, which builds code for menu option 1.




---------------------------------------------------------------------------------------------------------------------------------------------------------------

You'll be using Visual Studio Code to develop the initial version of a C# console application. You will be writing code that evaluates boolean expressions, implements various selection and iteration statements (branching and looping structures), and declares variables within code blocks at the appropriate scoping level for the app. Here, we'll discuss the overall goals of the project and how you'll build and test your application. We'll also cover how to set up your development environment, including a "Starter" code project.

## Project overview

The design specification for the Contoso Pets application identifies the following:

- the application will be a C# console application
- the application data will be accessible from a multidimensional string array named ourAnimals
- the ourAnimals array will include the following "pet characteristics" for each animal:

    - pet ID #
    - pet species (cat or dog)
    - pet age (years)
    - a description of the pet's physical condition/characteristics
    - a description of the pet's personality
    - the pet's nickname

- the application will load a sample dataset that represents dogs and cats currently in your care
- the application will present a list of menu options that enable an app user to access the main features of the application
- the application will include the following features:

    - list the pet information for all animals in the ourAnimals array
    - add new animals to the ourAnimals array (the following conditions apply)

        - an animal's age and some physical characteristics for a pet may be unknown until a veterinarian's examination (for example: breed, neutered/spayed status)
        - an animal's nickname and personality may be unknown when a pet first arrives
        - the pet species (dog or cat) must be entered when a new animal is added to the ourAnimals array
        - a pet ID must be programmatically generated when a new animal is added to the ourAnimals array

    - ensure animal ages and physical descriptions are complete (this action can occur after a veterinarian's examination)
    - ensure animal nicknames and personality descriptions are complete (this action can occur after the team gets to know a pet)
    - edit an animal’s age (if a pet's birth date is known and the pet has a birthday while in our care)
    - edit an animal’s personality description (a pet may behave differently after spending more time in our care)
    - display all cats that meet user specified physical characteristics 
    - display all dogs that meet user specified physical characteristics 

Some initial code development has already been completed. The Starter code project for this Guided project module includes a Program.cs file that provides the following code features:

- the code declares variables used to collect and process pet data and menu item selections
- the code declares the ourAnimals array
- the code uses a for loop around an if-elseif-else construct to populate the ourAnimals array with a sample dataset
- the code displays the following main menu options for user selection:

    1. List all of our current pet information
    1. Assign values to the ourAnimals array fields
    1. Ensure animal ages and physical descriptions are complete
    1. Ensure animal nicknames and personality descriptions are complete
    1. Edit an animal’s age
    1. Edit an animal’s personality description
    1. Display all cats with a specified characteristic
    1. Display all dogs with a specified characteristic

    Enter menu item selection or type "Exit" to exit the program

- the code reads the user's menu item selection and displays a message echoing their selection

Your goal is to update the existing code, and then develop app features in support of the first two menu options shown above. The key tasks that you'll need to accomplish are:

1. Update the code that's used to create the sample data for the app
1. Construct a loop around the main menu and create a selection statement that establishes a code branch for each menu option
1. Write the code to display all ourAnimals array data (menu option 1)
1. Build a loop for entering new ourAnimals array data (menu option 2 - part 1)
1. Write code to read and save new ourAnimals array data (menu option 2 - part 2)

You will use Visual Studio Code as your development environment, and you will test your application at each stage of your development process.

## Setup

Use the following steps to prepare for the Guided project exercises.

1. Notice that the GitHub repo for this Module includes the following folders:

    The **M06-guided-project-develop-conditional-branching-looping** folder contains the following folders:

    ```Output
    includes
    LabFiles
    ```

    The **includes** folder contain the training materials.

    The **LabFiles** folder contains console applications related to this Guided project module. The **Starter** folder contains the code that you will start with for this coding project. The **Final** folder contains the solution code. You should not need the solution code to finish the Guided project.

1. Use Visual Studio Code to create a new console app.

1. Open the **LabFiles** folder, and then open the **Starter** folder.

    The **Starter** folder contains a Program.cs file.

1. Copy the contents of the Program.cs file to the clipboard.

1. Switch to the new console application that you created, and then open the Program.cs file.

    The default Program.cs file is a Hello World app.

1. Replace the contents of your new Program.cs file with the code that you copied to the clipboard.

You are now ready to begin the Guided project exercises. Good luck!
