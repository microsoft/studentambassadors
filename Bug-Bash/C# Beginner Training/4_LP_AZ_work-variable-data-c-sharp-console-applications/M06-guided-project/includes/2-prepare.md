---
title: Prepare for guided project
durationInMinutes: 5
---

You'll be using Visual Studio Code to develop a version of a C# console application. The application comes with the basic features that create sample data on pets available for adoption and is able to display the pet's information. The main feature to add is searching available dogs using a single search term. The secondary tasks include adding and displaying `suggestedDonation` data.

## Project overview

The design specification for the additional features to the Contoso Pets application identifies the following:

- **Add dog attribute search**
    - Gather input for the pet characteristic search term
    - Loop through the animals array and identify "dogs"
    - For each dog, combine the the physical and personality descriptions for searching
    - search combined description for the input term match
    - Track and output the dogs that have a term match

- **Add *suggested donation* data**
    - Define `suggestedDonation` string
    - Expand the `ourAnimals` array to contain `suggestedDonation` and populate sample data with `suggestedDonation`
    - Ensure all usage of `ourAnimals` array accounts for added data
    - Output `suggestedDonation` with regional currency symbol ($, €, ¥,... )


Some initial code development has already been completed. The Starter code project for this Guided project module includes a Program.cs file that provides the following code features:

- the code declares variables used to collect and process pet data and menu item selections
- the code declares the ourAnimals array
- the code uses a for loop around an if-elseif-else construct to populate the ourAnimals array with a sample dataset
- the code displays the following main menu options for user selection:

    ```output
    1. List all of our current pet information
    2. Display all dogs with a specified characteristic

    Enter menu item selection or type "Exit" to exit the program```

- the code reads the user's menu item selection and displays a message echoing their selection. 
- only selection "1. List all of our current pet information" functions the starter code.

Your goal is to update the existing code to develop app features described above. The key features:
    - Add dog attribute search
    - Include suggested donation data

You will use Visual Studio Code as your development environment, and you will test your application at each stage of your development process.

## Setup

Use the following steps to prepare for the Guided project exercises.

1. Download a zip file containing the code folders for the LP3 Challenge project
    - In a browser, navigate to: <!-- TODO: Provide Link --> [Lab Files](../LabFiles/) and download the zip file.
1. Unzip the downloaded files locally (or in the sandbox if you are not using a local dev environment)
    - On your local machine, navigate to your downloads folder
    - Right-click the GuidedProject.zip file, and then select **Extract all**
    - Make note of the extracted files location (the location of the root folder)
1. Open the root GuidedProject folder in VS Code
    - Open VS Code locally (or open MS Learn sandbox and open VS Code if you are not using a local dev environment)
    - In VS Code, on the **File** menu, select **Open Folder**
    - Navigate to the folder that contains your extracted files, expand the folder structure to locate the folder named "GuidedProject".
    - Select **GuidedProject** and then select **Select Folder**

        The Visual Studio Code EXPLORER view should show the **GuidedProject** folder and two sub-folders named **Final** and **Starter**.

You are now ready to begin the Guided project exercises. Good luck!
