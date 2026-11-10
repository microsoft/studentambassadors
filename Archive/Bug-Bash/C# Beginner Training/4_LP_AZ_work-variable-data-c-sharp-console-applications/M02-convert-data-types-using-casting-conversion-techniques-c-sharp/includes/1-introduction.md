---
title: Introduction
durationInMinutes: 2
---

Frequently, when working with data, you'll need to change a value from one data type into another. There's many reasons why you might need to do this.

A simple example is any mathematical operation you want to perform with string data. You would first need to change the value into a numeric data type, like `int`, and then you could manipulate the operation. Alternatively, you may want to format and output a numeric value using string interpolation. Whether we're explicitly instructing the runtime to perform this change, or are relying on the runtime to implicitly change a value's data type, it's important to understand what is happening and why.

In this module, you'll use different techniques to change a data type when necessary. You'll learn when to use one technique over another, and when a given technique might risk the loss of data.

By the end of this module, you'll be able to take control of the data in your applications, knowing when to apply the correct technique to change data types as needed.

## Learning objectives

In this module, you'll:

- Use the casting operator to cast a value into a different data type.
- Use conversion methods to convert a value into a different data type.
- Guard against the loss of data when performing a cast or conversion operation.
- Use the `TryParse()` method to safely convert a string into a numeric data type.

## Prerequisites:

- Experience using data types like `string`, `int`, `decimal`, `float`, and so on
- Experience using arrays and the `foreach` iteration statement
- Experience using string interpolation to combine variable and literal values for output
