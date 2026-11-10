---
title:   Exercise - Install the .NET SDK
durationInMinutes: 3
---
The .NET developer platform is an open source developer platform for building different types of applications. It consists of the languages and libraries that you use to develop your apps. You can write .NET apps in C#, F#, or Visual Basic.

There are actually a few different .NET platforms that you can use to create different types of apps:

- .NET Core: (runs anywhere!) Windows, Linus, macOS
- .NET Framework: websites, services, and apps on Windows
- Xamarin/Mono: a .NET for mobile apps

There is also .NET Standard, which is the shared set of libraries based on the platforms listed above.

For C# apps, the .NET runtime is the code library that's required to run your applications. It is also called the Common Language Runtime or CLR. It is not required to *write* your code, but it is required to actually *run* your application.

## Check to see if .NET is installed

1. Ensure that you have Visual Studio Code open.

    You can use the Windows Start menu to locate and open Visual Studio Code.

1. On the **Terminal** menu, click **New Terminal**.

    We will be using the Terminal panel to enter a command. You could also use the standard Windows Command Prompt rather than the Visual Studio Code's built in Terminal if you wanted.

1. At the Terminal command prompt, type: **dotnet --version** and then press the Enter key.

    If a version of .NET is installed on your PC, this command will display the version number.

1. Take a moment to view the response to your dotnet --version command.

    If you receive an error message telling you that the term `dotnet` is not recognized, then you do not have the .NET SDK installed.

    If a version of .NET is already installed, you should see a response message listing the version number. It will be is similar to the following (depending on what version you have):

    `6.0.401`

1. Close Visual Studio Code.

## Install the .NET Software Development Kit

1. Open a new Internet browser window.

1. To open the download page for the .NET SDK, navigate to the following URL:

    [https://dotnet.microsoft.com/download/dotnet](https://dotnet.microsoft.com/download/dotnet)

1. On the **Download .NET** page, select **.NET 6.0**.

    Select the latest version that includes **Long Term Support**.

1. Select the download option that matches your operating system and computer processor.

    For example, if you are on a Windows machine with an x64 architecture microprocessor, select **x64**.

    Once you have selected the version matching your processor / platform, your browser will download the installation file.

1. Run the .NET SDK installation file.

    On a Windows PC, you can find your Downloads folder using File Explorer. Double-click the installation file to begin the installation process.

1. On the .NET SDK Installer window, click **Install**.

1. Wait for the installation to complete.

    Installation should only take about 20 seconds. Once installation is complete, you will see a screen confirming the installation was successful.

1. To close the installer window, click **Close**.

## Verify your installation

1. Open Visual Studio Code.

    > [!IMPORTANT]
    > Visual Studio Code will recognize whether .NET is installed when it starts up. If you had VisualStudio Code open when you installed .NET, you will need to close it and then open a new instance to ensure that it recognizes that .NET is installed.

1. On the **Terminal** menu, click **New Terminal**.

    You could also use the standard Windows Command Prompt rather than the Visual Studio Code's built in Terminal if you wanted.  

1. At the Terminal command prompt, type: **dotnet --version** and then press the Enter key.

1. Ensure that a .NET version number is listed.

    The version number will be similar to: `6.0.403`

    You are likely to see a more recent version number. But it should begin with `6.` if you installed .NET 6.

Congratulations, you did it! You are now ready to begin coding C# in Visual Studio Code.
