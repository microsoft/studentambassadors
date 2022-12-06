Unit Title: Exercise - Build and test a loop for entering new pet data
-----------------------------------------------------------------------------------------------------------------------------------------------

In this step of our development process, we will begin working on the feature of our application that enables the user to add new animals to the ourAnimals array. To get started, we will first work on calculating the initial values of our loop control variables. We will then focus on constructing the loop that enables our app to collect user specified data for the animals. The detailed tasks that we will complete during this exercise are:

1. Calculate petCount: write code that counts the number of pets in the ourAnimals array that have assigned data.
1. Conditional messages: write code to display message output when petCount is less than maxPets.
1. Outer loop: build a loop structure that will be used for entering new ourAnimals array data.
1. Exit criteria: write code that evaluates the exit condition for the "enter new ourAnimals array data" loop.
1. Verification test: perform verification tests for the code that you have developed in this exercise.

> [!IMPORTANT]
> You must complete the previous exercise in this module before starting this exercise.

## Count the number of pets in the ourAnimals array

In this task, we will declare variables that establish the exit criteria for our data entry loop and we will create a `for` loop that we will use to count the number of pets in `ourAnimals` that have been assigned data. Let's get started.

1. Ensure that you have Visual Studio Code open, and that your Program.cs file is visible in the Editor.

1. Locate the `switch(menuSelection)` statement, and then find the `case "2":` code line.

1. Locate the `Console.WriteLine()` statement that displays the "coming soon" message, and then replace it with a blank code line.

1. On the blank code line that you just created, to declare (and initialize) the `anotherPet` and `petCount` variables, enter the following code:

    ```c#
    string anotherPet = "y";
    int petCount = 0;
    ```

    We will be using these two variables to control our (upcoming) while loop iterations when the user is entering new pet data. We initialize both variables as part of the declaration. Let's look at how they will be used.

    - `anotherPet` is initialized with a value of `y` prior to the start of the `while` loop. It will receive a user assigned value, either `y` or `n` inside the `while` loop.

    - `petCount` represents the number of animals with assigned pet characteristics. It will be assigned a calculated value outside of our `while` loop, and will be incremented by 1 inside the `while` loop each time a new animal is added to the ourAnimals array.

    > [!IMPORTANT]
    > We could have chosen to declare `petCount` at the application level rather than scoping it to our `case "2":` selection. This would have enabled us to access `petCount` from anywhere in our Contoso Pets application. For example, if we had scoped `petCount` at the application level, we could have chosen to assign a value to `petCount` when we created our sample data, and then programmatically manage its value throughout the remainder of our code. We could have also maintained the value of `petCount` in the code that removes pets from the ourAnimals array (for example, when we find our pets a new home). The question is, at what level should we scope a variable (such as `petCount`) when we are considering whether we want to have access to the variable in other parts of our code? It might be tempting to scope `petCount` at the highest level of our application, just in case we decide to use it elsewhere. After all, that would ensure that `petCount` is available anywhere in our application. Maybe we should scope other variables at the application level as well. That way, they would never go out of scope and we would know that their value would be accessible when we need it. So why don't we just scope variables at the application level if we think that we might need again later? It's because scoping variables at a higher level than necessary can lead to serious problems for our app. For example, it will inflate the resource requirements for our application and may expose our application to unnecessary security risks. As your applications become larger and more complex, the resources that they require will increase. And as your applications become more "real-world", they will become more accessible, maybe accessible from the cloud or other applications. These days we tend to run lots of applications simultaneously, and since we also tend to leave our application running even when we aren't actively using them, keeping app's resource requirements under control and our app's security footprint as small as possible are both important. Sure, modern operating systems do a great job of managing resources and securing our applications, but it's still best practice to keep our variables scoped to the level where they are actually needed. In our Contoso Pets app, if we decide to use `petCount` more broadly within our application, we can update our code to scope our `petCount` variable at a higher level. The important thing to remember is to keep your variables scoped as narrowly as possible, and only increase their scope when it becomes necessary (not before).

1. On the code line below your variable declarations, to create a loop that iterates through the animals in the ourAnimals array, enter the following code:

    ```c#
    for (int i = 0; i < maxPets; i++)
    {
    }
    ```

    This code should look familiar. We will use this same `for` loop each time we need to iterate through the animals in the ourAnimals array.

1. Inside the code block of our `for` loop, to check whether pet characteristics data has been assigned to an animal, enter the following code:

    ```c#
    if (ourAnimals[i, 0] != "ID #: ")
    {
    }
    ```

    Again, this code should look familiar. We will use this same `if` statement whenever we want to know if data has been assigned to an animal in the ourAnimals array.

1. Inside the code block of the `if` that you just created, to increment `petCount` by 1, enter the following code:

    ```c#
    petCount += 1;
    ```

1. Take a minute to examine your completed `for` loop.

    Your completed `for` loop code should look like the following code:

    ```c#
    for (int i = 0; i < maxPets; i++)
    {
        if (ourAnimals[i, 0] != "ID #: ")
        {
            petCount += 1;
        }
    }
    ```

    This code will loop through the ourAnimals array checking for assigned data. When it finds an animal with data assigned, it increments `petCounter`.

1. On the Visual Studio Code **File** menu, select **Save**.

1. Open the Integrated Terminal panel in Visual Studio Code and enter the command to Build your program.

    To open the Integrate Terminal from the EXPLORER view, right-click **Starter**, and then select **Open in Integrated Terminal**. You can also use the **View** or **Terminal** menu to open the Integrated Terminal panel.

    To Build your program, enter the `dotnet build` command from the Terminal command prompt.

1. Fix any Build errors that you see reported before continuing.

    > [!NOTE]
    > For now, you can ignore the Warning message about `anotherPet` being assigned but never used. We will add code that uses `anotherPet` later in this exercise.

    If you have any build errors, remember that the Build error and warning messages tell you what the issue is and where you can find it. If you update your code, remember to save your changes before you rebuild.

1. Close the Terminal panel.

## Display message output when petCount is less than maxPets

In this task, we will check to see if `petCount` is less than `maxPets` and if it is, we will display a message for the user. Let's get started.

1. On a blank code line below the `for` loop that you just created, to see if `petCount` is less than `maxPets`, enter the following code:

    ```c#
    if (petCount < maxPets)
    {
    }
    ```

1. Inside the code block of the `if` statement, to display a message to the user, enter the following code:

    ```c#
    Console.WriteLine($"We currently have {petCount} pets that need homes. We can manage {(maxPets - petCount)} more.");
    ```

    This message provides some important context to the app user as they are about to enter information for pets that will be added to the ourAnimals array.

1. Take a minute to review the code the `case "2":` code branch of your `switch` statement.

    At this point, your `case "2":` code branch should look like the following:

    ```c#
    case "2":
        // Add a new animal friend to the ourAnimals array
        string anotherPet = "y";
        int petCount = 0;
        for (int i = 0; i < maxPets; i++)
        {
            if (ourAnimals[i, 0] != "ID #: ")
            {
                    petCount += 1;
            }

        }

        if (petCount < maxPets)
        {
            Console.WriteLine($"We currently have {petCount} pets that need homes. We can manage {(maxPets - petCount)} more.");
        }

        Console.WriteLine("Press the Enter key to continue.");
        readResult = Console.ReadLine();
        break;
    ```

1. On the Visual Studio Code **File** menu, select **Save**.

1. Open the Integrated Terminal panel in Visual Studio Code and enter the command to Build your program.

1. Fix any Build errors that you see reported before continuing.

    Again, you can ignore the Warning message about `anotherPet` being assigned but never used. In the next task, you will start building the `while` loop that is used to enter the data for one or more pets. The expression that you create for the `while` loop will use `anotherPet` and this Warning message will go away.

    Remember, warning messages are things that you should be concerned about, but they won't prevent you from running your program.

1. At the Terminal command prompt, enter the command to run your program.

    Enter the `dotnet run` command at the Terminal command prompt to run your program code.

    As long as your code doesn't generate a runtime error, the main menu of the app should now be displayed in the Terminal panel.

1. At the Terminal command prompt, enter **2**

    This should cause your `case "2":` code branch to run.

1. Verify that the following message is displayed in the Terminal.

    ```txt
    We currently have 4 pets that need homes. We can manage 4 more.
    Press the Enter key to continue.
    ```

    If you don't see the expected message displayed, review your code to identify and fix the issue. Save your changes, rebuild, and run the app again. Be sure to get code working as expected before you continue.  

1. At the Terminal command prompt, press Enter to continue running your application.

1. Exit the application, and then close the Terminal panel.

## Build a loop structure that will be used for entering new ourAnimals array data

In this task, we will create a `while` loop that continues to iterate as long as `anotherPet` is equal to `y` AND `petCount` is less than `maxPets`. Let's get started.

1. In the code Editor, create a blank code line below your `if (petCount < maxPets)` code block.

1. To begin the process of creating your new `while` loop, enter the following code:

    ```c#
    while (anotherPet == "y" && petCount < maxPets)
    {
    }
    ```

1. On the Visual Studio Code **File** menu, select **Save**.

1. Open the Integrated Terminal panel in Visual Studio Code and enter the command to Build your program.

1. Notice that you no longer receive the Warning message about `anotherPet` not being used.

    If any Build errors or warnings were reported, fix the issues before continuing.

## Check exit condition for new pets loop

In this task, we will add code inside our `while (anotherPet == "y" && petCount < maxPets)` loop that increments `petCount` and then checks whether `petCount` is still less than `maxPets`. If `petCount` is still less than `maxPets`, we will ask the user if they want to enter information for another pet, and ensure that their response is either `y` or `n`. Finally, after the end of our `while (anotherPet == "y" && petCount < maxPets)` code block, but before the `break;` statement that separates `case "2";` from `case "3";`, we will update the message to the user, making it conditional on the value of `petCount`. Let's get started.

> [!NOTE]
> We are deliberately postponing the development of code that manages pet data entry by the user. We will develop that code in the next exercise. For now we will increment `petCount` as is data were being entered and saved to the ourAnimals array. This enables us to finish developing the code logic associated with our `while` loop.

1. Create a blank code line inside the code block of the `while (anotherPet == "y" && petCount < maxPets)` loop that you created in the previous task.

1. To increment `petCount`, enter the following code:

    ```c#
    // increment petCount (the array is zero-based, so we increment the counter after adding to the array)
    petCount = petCount + 1;
    ```

1. To check whether `petCount` is less than `maxPets`, enter the following code:

    ```c#
    // check maxPet limit
    if (petCount < maxPets)
    {
    }
    ```

1. Inside the code block of the `if` statement that you just created, to ask the user whether they want to add another pet, enter the following code:

    ```c#
    // another pet?
    Console.WriteLine("Do you want to enter info for another pet (y/n)");
    ```

1. Below the `WriteLine()` message that you just entered, to read the user response and ensure that the user entered "y" or "n", enter the following code:

    ```c#
    do
    {
        readResult = Console.ReadLine();
        if (readResult != null)
        {
            anotherPet = readResult.ToLower();
        }

    } while (anotherPet != "y" && anotherPet != "n");
    ```

1. Locate the `break` statement that separates `case "2";` from `case "3";` in your `switch` statement.

1. Notice the `Console.WriteLine()` message and `Console.ReadLine()` that are used to pause the app at the end of our `case "2";` code.

1. To enclose the code that we're using to pause the app inside an `if` statement, update your code as follows:

    ```c#

    if (petCount >= maxPets)
    {
        Console.WriteLine("Press the Enter key to continue.");
        readResult = Console.ReadLine();
    }

    break;

    case "3":
    ```

1. To let the user know that the pet they just added puts Contoso Pets at their capacity limit, update your code as follows:

    ```c#

        if (petCount >= maxPets)
        {
            Console.WriteLine("We have reached our limit on the number of pets that we can manage.");
            Console.WriteLine("Press the Enter key to continue.");
            readResult = Console.ReadLine();
        }

        break;

    case "3":
    ```

1. Take a minute to review the code for your `while` loop and the user message that you've created.

    Your `while (anotherPet == "y" && petCount < maxPets)` loop and code that displays the user message should look like the following

    ```c#
    while (anotherPet == "y" && petCount < maxPets)
    {
        // increment petCount (the array is zero-based, so we increment the counter after adding to the array)
        petCount = petCount + 1;

        // check maxPet limit
        if (petCount < maxPets)
        {
            // another pet?
            Console.WriteLine("Do you want to enter info for another pet (y/n)");
            do
            {
                readResult = Console.ReadLine();
                if (readResult != null)
                {
                    anotherPet = readResult.ToLower();
                }

            } while (anotherPet != "y" && anotherPet != "n");
        }
    }

    if (petCount >= maxPets)
    {
        Console.WriteLine("We have reached our limit on the number of pets that we can manage.");
        Console.WriteLine("Press the Enter key to continue.");
        readResult = Console.ReadLine();
    }
    ```

1. On the Visual Studio Code **File** menu, select **Save**.

1. Open the Integrated Terminal panel in Visual Studio Code and enter the command to Build your program.

1. Fix any Build errors or warnings that you see reported before continuing.

## Check your work

In this task, we will run our application from the Integrated Terminal and verify that the looping and branching logic that we've created works as expected. Let's get started.

1. If necessary, open Visual Studio Code's Integrated Terminal panel.

1. At the Terminal command prompt, enter **dotnet run**

1. At the Terminal command prompt, enter **2**

1. Verify that you see the following messages:

    ```txt
    We currently have 4 pets that need homes. We can manage 4 more.
    Do you want to enter info for another pet (y/n)
    ```

1. At the Terminal command prompt, enter **n**

1. Verify that your code exits the loop for entering new pets when you entered "n".

    If your code logic is working as expected, you should see the main menu displayed in the Terminal.

    If your code does not exit the loop when expected, press **Ctrl + C** in the Terminal to force execution to stop. You need to step through your code manually and trace the values of the exit criteria variables. Update your code if necessary to ensure that you exit the `while` loop when the user enters "n" (even when petCount < maxPets). Save your changes, rebuild your program, and run through the verification test to arrive back at this point.

1. At the Terminal command prompt, enter **2**

    Once again, you will see the following messages displayed:

    ```txt
    We currently have 4 pets that need homes. We can manage 4 more.
    Do you want to enter info for another pet (y/n)
    ```

1. At the Terminal command prompt, enter **y**

1. Take a minute to consider how your code is assigning the value to `petCount` and how that value compares with the zero-based index number that is used to access/assign values of the `ourAnimals` array.

    So, what do we know about the value assigned to `petCount` and why do we need consider how our code uses the value? Well, understanding the logic that's being implemented by our applications is important. Let's take a look at what we know and why it's important:

    - We know that `petCount` is 4 when we enter the first iteration of the while loop (our code displays a message telling us that we have 4 pets that need homes).
    - We also know that we increment `petCount` after we store new data to the array (we don't actually enter and store data yet, but that is our plan).  
    - Let's consider how these two things affect our storage of data to the `ourAnimals` array:

        - We will store new data to the array when the value of `petCount` is 4. But we already have data for 4 pets. Do we have a problem? When we remember that the array elements are zero-based, our code logic makes sense. For example, `ourAnimals[0,0]` contains the value of the pet ID for animal 1. So it follows that `ourAnimals[3,0]` contains the value of the pet ID for animal 4. That means that we store data for pet 5 when petCount is 4. Perfect.
        - Since our code will be storing pet data to the array before it increments `petCount`, and since the code increments `petCount` before prompting us if we want to enter data for another pet, when we see the **Do you want to enter info for another pet (y/n)** prompt for the first time, `petCount` is already set to 5.

    - So after we enter **y** at the command prompt (which we just did in our code verification test), we also know that:

        - our `while (anotherPet == "y" && petCount < maxPets)` loop will iterate. We know that it will iterate because we know that `anotherPet == "y"` and `petCount < maxPets`.
        - when our while loop iterates, the value assigned to `petCount` will be incremented.
        - so we know that after we enter **y** the first time, the value assigned to `petCount` will be 6.

    With all that in mind, let's continue our testing.

1. Notice that the Terminal panel updates with the same "another pet?" message, but does not give us an updated `petCount`.

    The Terminal panel should have updated to show the following:

    ```txt
    We currently have 4 pets that need homes. We can manage 4 more.
    Do you want to enter info for another pet (y/n)
    y
    Do you want to enter info for another pet (y/n)
    ```

1. At the Terminal command prompt, enter **y**

    When we enter `y` a second time, `petCount` is incremented to 7. Still less than `maxPets`

1. At the Terminal command prompt, enter **y**

    When we enter `y` a third time, `petCount` is incremented to 8. So `petCount` is now equal to `maxPets`

1. Verify that your code exits the loop for entering new pets after you enter **y** the third time, and that the Terminal has updated as follows:

    ```txt
    We currently have 4 pets that need homes. We can manage 4 more.
    Do you want to enter info for another pet (y/n)
    y
    Do you want to enter info for another pet (y/n)
    y
    Do you want to enter info for another pet (y/n)
    y
    We have reached our limit on the number of pets that we can manage.
    Press the Enter key to continue.
    ```

    If your code does not exit the loop when expected, step through your code manually and trace the values of the exit criteria variables. Update your code if necessary to ensure that you exit the loop when petCount reaches a value that is equal to maxPets (keep answering "y" until you know that petCount is equal to maxPets, which has a default value of 8).

1. At the Terminal command prompt, press Enter to continue running your application.

1. Exit the application, and then close the Terminal panel.
