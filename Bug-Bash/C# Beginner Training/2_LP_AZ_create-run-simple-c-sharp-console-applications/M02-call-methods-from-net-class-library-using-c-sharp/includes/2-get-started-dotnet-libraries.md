---
title:   Get started with .NET Libraries
durationInMinutes: 3
---
There's more to building applications than the C# language itself. You'll also need the .NET Runtime, which hosts and manages your code as it executes on the end user's computer. You'll also rely on a collection of coding resources called the .NET Class Library that you can use in your applications. This unit explains what the .NET Class Library is and how it complements the C# programming language.

## What is the .NET Class Library?

The **.NET Class Library** is a collection of thousands of classes containing tens of thousands of methods. These methods are created by Microsoft and are available for use in your applications.

You can think of a class as a container for methods. Developers typically keep related methods together in a single class. For example, any methods that can send or receive information from a command-line window are collected into the `System.Console` class in the .NET Class Library.

In many cases, these classes and methods enable you to build a specific type of application. For example, one of the larger subsets of classes and methods enable you to create dynamic web applications. There's several families of classes that enable you to build native desktop applications. Another subset of classes and methods enable you to access a database.

There are other classes with methods that provide support in a more general way. In other words, their utility spans a wide range of device platforms, application frameworks, and technology areas. For example, if you want to read or write file information, or perform trigonometry or calculus operations, there are general purpose classes/methods that you can use in your code. It doesn't matter whether you're building applications for the web, desktop, mobile device, or the cloud, general purpose classes and methods are there to help.

As you can imagine, having a massive library of functionality available to your applications is a huge time saver for you as a software developer.

### Even data types are part of the .NET Class Library

The C# data types you've already learned about are actually part of the .NET Class Library. The C# language masks the connection between the data types we've used and the .NET classes in order to simplify our work. However, behind the scenes, the data types are implemented just like every other class in the .NET Class Library. This connection provides our everyday variables with built-in methods that can be very helpful.

## How to find what you need in the .NET Class Library

With so many classes and methods, how can you find what you need for your application?

First of all, there's a small subset of classes you'll likely use throughout your tenure as a C# software developer. Depending on the projects you work on, you'll become more familiar with some parts of the .NET Class Library and less familiar with others. No one knows it all, not even people that work at Microsoft.

Second, as you have a need, you'll likely use your favorite search engine to find blog posts, articles, or forums where other users have needed to do things that are similar what you want to do. Third-party sources will give you clues and even provide some sample code you can try.

Next, you'll likely spend time reading Microsoft's own documentation for specific methods to understand exactly what they do, how they work, what are their limitations, under what conditions they'll raise exceptions (errors) and how you mitigate those problems. The documentation will become your source of truth for the .NET Class Library. The documentation team works closely with the .NET Class Library's software developers to ensure its accuracy.

Finally, you'll begin to experiment with small code projects to deepen your understanding of how the classes and methods work.

All software developers follow a similar process when stepping into unfamiliar territory. The process of discovery is enjoyable, albeit challenging.

## Recap

- The .NET Class Library supplies us with a wealth of functionality that we can use by merely referencing the classes and methods we need.
- Even our data types are part of the .NET Class Library. C# merely provides an alias for those data types.

## quiz title: Check your knowledge

## Multiple Choice

How do you find information on the .NET classes and methods you will be using?
( ) .NET Class Library. {{Incorrect. Although it is true that reference material on classes and methods are found in the .NET Class Library, this answer is not complete.}}
( ) Developer websites. {{Incorrect. Although partially correct, this answer is incomplete.}}
(x) .NET Class Library, Google search, and developer websites. {{Correct! This answer hits the big 3: .NET Class Library, Google search, and developer websites. These tools are the best way to find information on .NET classes and methods.}}
