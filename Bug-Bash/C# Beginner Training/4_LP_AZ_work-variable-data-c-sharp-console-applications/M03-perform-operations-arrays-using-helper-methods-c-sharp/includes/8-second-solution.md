---
title: Review the second solution
durationInMinutes: 1
---

The following code is one possible solution for the challenge from the previous unit.

```c#
string orderStream = "B123,C234,A345,C15,B177,G3003,C235,B179";
string[] items = orderStream.Split(',');

foreach (var item in items)
{
    if (item.StartsWith("B"))
    {
        Console.WriteLine(item);
    }
}

```

This code is merely "*one possible solution*" because we didn't specify which technique to apply to which line of output. You could have used either the `Console.WriteLine()` or `Console.Write()` methods to produce the desired output.

```Output
B123
B177
B179

```

If you were successful, congratulations! Continue to the knowledge check in the next unit.

> [!IMPORTANT]
> If you had trouble completing this challenge, you should review the previous units before you continue. All new ideas we describe in other modules will depend upon your understanding of the ideas in this module.
