---
title: Choose the right data type
durationInMinutes: 8
---

You've been introduced to the difference between value types and reference types, as well as integral and floating point types.

Suppose your job is to build a new application that retrieves, manipulates, and stores different types of data. Which data types will you choose.

In some cases, it will be an easy choice. For example, when you need to work with text, then you'll likely default to using the `string` data type unless you need to perform a significant amount of concatenation.

But what about working with numeric data? There are 11 different options. How do you choose the right data type?

## How do you choose the right data type?

With so many data types to choose from, what criteria should you use to choose the right data type for the particular situation?

When evaluating your options, you must weigh several important considerations. Often there's no one single correct answer, but some answers are more correct than others.

- **Choose the data type that has the desired value range as a built-in constraint in your application.** Your choice of a data type can help to set the boundaries for the size of the data you might store in that particular variable. For example, if you know a particular variable should only store a number between 1 and 10,000 otherwise it's outside of the boundaries of what would be expected, you would likely avoid `byte`, `sbyte` since their ranges are too low. Furthermore, you would likely not need `int`, `long`, `uint`, and `ulong` because they can store much more data than is necessary. Likewise, you would probably skip `float`, `double`, and `decimal` if you didn't need fractional values. You might narrow it down to `short` and `ushort`, both of which may be viable given the circumstances. If you're confident that a negative value would have no meaning in your application, you might choose `ushort`. Now, any value assigned to a variable of type `ushort` outside of the boundary of 0 to 65535 would throw an exception, thereby subtly helping you enforce a degree of sanity checking in your application.
- **Don't choose the data type based on what you perceive will be the impact to performance (at least, not at first).** You may be tempted to choose the data type that uses the fewest bits to store data thinking it will improve your application's performance. However, some of the best advice related to application performance (that is, how fast your application runs) is to not "prematurely optimize". In other words, you should resist the temptation to guess at the parts of your code, including the selection of data types, that may impact your application's performance. Many assume that because a given data type stores less information it must use less of the computer's processor and memory than a data type that stores more information. Instead, you should choose the right fit for your data, then later you can empirically measure the performance of your application using special software that provides factual insights to the parts of your application that negatively impact performance.
- **Choose the data type based on the interaction with library functions and the data types of their inputs and outputs.** Suppose you want to work with a span of years between two dates. Given that this is a business application, you might determine that you only need a range from about 1960 to 2200. This might lead you to work with `byte` since it can represent numbers between 0 and 255. However, when you look at the built-in methods on the `System.TimeSpan` and `System.DateTime` classes, you realize they mostly accept values of type `double` and `int`. If you choose `sbyte`, you'll constantly be casting back and forth between `sbyte` and `double` or `int`. In this case, it might make more sense to choose `int` if you don't need subsecond precision, and `double` if you do need subsecond precision.
- **Choose the data type based on the impact to other systems such as long-term storage in a database.** Sometimes, you must consider how the information will be consumed by other applications or other systems like a database. For example, SQL Server's type system is different from C#'s type system. As a result, some mapping between the two must happen before you can save data into that database. If your application's purpose is to interface with a database, then you would likely need to consider how the data will be stored, how much data will be stored, and how choosing a larger data type might impact the amount (and cost) of the physical storage required to store all the data your application will generate.
- **When in doubt, stick with the basics.** While we have looked at several considerations, which often lead you to consider many different data types, as you're getting started, for simplicity's sake you should prefer a subset of basic data types, including:
  - `int` for most whole numbers
  - `decimal` for numbers representing money
  - `bool` for true or false values
  - `string` for alphanumeric value
- **Choose specialty complex types for special situations.** Don't reinvent data types if ones already exist for a given purpose.
  - `byte` for working with encoded data that comes from other computer systems or using different character sets.
  - `double` for working with geometric or scientific purposes. `double` is used frequently when building games involving motion.
  - `System.StringBuilder` to build a single string from lots of literals or other variables. We'll cover this in more detail in the module "Modify content of strings using built-in string data type methods in C#".
  - `System.DateTime` for a specific date and time value. We'll cover this in more detail in the module "Manipulate date and time data using the DateTime and TimeSpan classes in C#".
  - `System.TimeSpan` for a span of years / months / days / hours / minutes / seconds / milliseconds. We'll cover this in more detail in the module "Manipulate date and time data using the DateTime and TimeSpan classes in C#".

## Recap

- There's several considerations when choosing data types for your code. However, while you should be careful and think through your choices, if you stick with some of the basic types like `int`, `decimal`, `string`, and `bool`, you'll likely be fine.