---
title:  Review the solution for the nested iteration and selection statements challenge activity
durationInMinutes: 3
---
The following code is one possible solution for the challenge from the previous unit.

```c#
string[] orderIDs = { "B123", "C234", "A345", "C15", "B177", "G3003", "C235", "B179" };

foreach (string orderID in orderIDs)
{
    if (orderID.StartsWith("B"))
    {
        Console.WriteLine(orderID);
    }
}
```

This code is merely "*one possible solution*" because a lot depends on how you decided to implement the logic. As long as you got the right results per the rules in the challenge, and you used an array and a foreach statement, then you did great!

If you succeeded, congratulations! Continue on to the knowledge check in the next unit.

> [!IMPORTANT]
> If you had trouble completing this challenge, maybe you should review the previous units before you continue on. All new ideas we discuss in other modules will depend on your understanding of the ideas that were presented in this module.
