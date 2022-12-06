Code challenges throughout these modules will reinforce what you've learned and help you gain some confidence before continuing on.

## Complicated Permissions Challenge

In this challenge, you'll implement business rules that restrict access to users based on their permissions and their level. You'll display a different message to the user depending on their permissions and level.

### Step 1: Initialize permission and level values

1. Ensure that you have an empty Program.cs file open in Visual Studio Code.

    If necessary, open Visual Studio Code, and then complete the following steps to prepare a Program.cs file in the Editor:

    1. On the **File** menu, select **Open Folder**.

    1. Use the Open Folder dialog to navigate to, and then open, the **CsharpProjects** folder.

    1. In the Visual Studio Code EXPLORER panel, select **Program.cs**.

    1. On the Visual Studio Code **Selection** menu, select **Select All**, and then press the Delete key.

1. Type the following code into the Visual Studio Code Editor.

    ```c#
    string permission = "Admin|Manager";
    int level = 55;
    ```

1. Review the initial code lines

    A combination of `permission` and `level` will be used to define the access rules in this challenge scenario. You can use these two variables in your solution.

    The full list of conditions for business rules will be specified in the next step. To sufficiently test all of the scenarios described in Step 2, you may need to test the code with additional data values.

### Step 2 - Implement business rules

Here are the **Business Rules** that your solution must satisfy:

> [!IMPORTANT]
> Use the `Contains()` helper method of a string to determine whether the value of `permission` contains one of the permission values specified under "business rules". Example: `permission.Contains("Admin")` will return `true` when using the data values for initial testing.

1. If the user is an Admin with a level greater than 55, output the message:

   ```Output
   Welcome, Super Admin user.
   ```

2. If the user is an Admin with a level less than or equal to 55, output the message:

   ```Output
   Welcome, Admin user.
   ```

3. If the user is a Manager with a level 20 or greater, output the message:

   ```Output
   Contact an Admin for access.
   ```

4. If the user is a Manager with a level less than 20, output the message:

   ```Output
   You do not have sufficient privileges.
   ```

5. If the user is not an Admin or a Manager, output the message:

   ```Output
   You do not have sufficient privileges.
   ```

### Step 3 - Test your solution using the initial data values suggested

1. Save your solution code.

1. Build and run your code.

1. Evaluate the output.

    When you run your code, including the initial configuration data from Step 2, you should see the following output:

    ```Output
    Welcome, Admin user.
    ```

### Step 4 - Test for the other business rules

1. Update the values assigned to permission and level.

1. Save and run the code.

1. Evaluate the output to verify the other business rules are satisfied.

Whether you get stuck and need to peek at the solution or you finish successfully, continue on to view a solution to this challenge.
