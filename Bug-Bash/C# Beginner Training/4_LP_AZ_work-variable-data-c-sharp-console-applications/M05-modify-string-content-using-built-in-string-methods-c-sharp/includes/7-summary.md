---
title: Summary
durationInMinutes: 2
---

Our goal was to extract, remove, and replace values in strings. At the outset, we said that often the data we receive has extraneous data or characters that we'll need to avoid or eliminate before we can use the target data.

Utilizing the `IndexOf()` method, we could identify the position of a character or string within another string. This was the first building block to using the `Substring()` method to extract a portion of a string given the starting position and the number of characters to extract (the length). It also enabled us to use the `Remove()` method to eliminate characters from a string given the starting position and the length. We learned of variations like `LastIndexOf()` method to find the last position of a character of string within another string, and the `IndexOfAny()` to find the position of any value of a given `char` array. We used the `while` statement to iterate through a longer string to find and extract all instances of a character or string within a larger source string. Finally, we used the `Replace()` method to swap all instances of a character or string inside of a larger string.

While it might be possible to perform these kinds of operations using a `char` array, iterating through each `char` to find matches, keeping track of the starting and ending points we wanted to locate, and so on. It would take many more steps to accomplish what these string helper methods can accomplish in a single call.
