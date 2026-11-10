---
title: Review the solution to the improve code readability challenge activity
durationInMinutes: 3
---
The following code is one possible solution for the challenge from the previous unit.

```c#
/*
   This code reverses a message, counts the number of times 
   a particular character appears, then prints the results
   to the console window.
 */

string originalMessage = "The quick brown fox jumps over the lazy dog.";

char[] message = originalMessage.ToCharArray();
Array.Reverse(message);

int letterCount = 0;

foreach (char letter in message)
{
    if (letter == 'o')
    {
        letterCount++;
    }
}

string newMessage = new String(message);

Console.WriteLine(newMessage);
Console.WriteLine($"'o' appears {letterCount} times.");
```

This code is merely "*one possible solution*". You may have come up with some different variable names and different vertical spacing and tab indentation. Here's a list of changes that were made.

- We added a higher-level description of what the entire code listing is attempting to accomplish in a multi-line comment at the top. We could argue that this is a small improvement over the original code comments, however given the challenge's description of the code, there wasn't much more context available.
- We removed the individual comments because they weren't providing any real insight into the code's purpose or function.
- We added several blank lines to improve the phrasing of the code listing. We tried to keep lines together that were similar or that worked together to accomplish some small task.
- We used line feeds and tabs to improve the `for` statement and the `if` statement.
- We used local variable naming conventions to better convey the purpose of each value.

If you identified the same issues and addressed them in a similar way, congratulations! Continue on to the knowledge check in the next unit.

> [!IMPORTANT]
> If you had trouble completing this challenge, maybe you should review the previous units before you continue on. All new ideas we discuss in other modules will depend on your understanding of the ideas that were presented in this module.
