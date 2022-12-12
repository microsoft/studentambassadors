---
title: Review the first solution
durationInMinutes: 1
---

The following code is one possible solution for the challenge from the previous unit.

```c#
string[] values = { "12.3", "45", "ABC", "11", "DEF" };

decimal total = 0m;
string message = "";

foreach (var value in values)
{
    decimal number; // stores the TryParse "out" value
    if (decimal.TryParse(value, out number))
    {
        total += number;
    } else
    {
        message += value;
    }
}

Console.WriteLine($"Message: {message}");
Console.WriteLine($"Total: {total}");
```

This code is merely "*one possible solution*" because there's likely several ways to solve this challenge. The proposed solution (above) relies on TryParse(), however it's possible you have another approach that works equally well. Just make sure your result matches the following output:

```Output
Message: ABCDEF
Total: 68.3
```

If you were successful, congratulations! Continue on to the knowledge check in the next unit.

> [!IMPORTANT]
> If you had trouble completing this challenge, maybe you should review the previous units before you continue on. All new ideas we discuss in other modules will depend on your understanding of the ideas that were presented in this module.
