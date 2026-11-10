The following code is one possible solution for the challenge from the previous unit.

```c#
int hero = 10;
int monster = 10;

Random dice = new Random();

do
{
    int roll = dice.Next(1, 11);
    monster -= roll;
    Console.WriteLine($"Monster was damaged and lost {roll} health and now has {monster} health.");

    if (monster <= 0) continue;

    roll = dice.Next(1, 11);
    hero -= roll;
    Console.WriteLine($"Hero was damaged and lost {roll} health and now has {hero} health.");

} while (hero > 0 && monster > 0);

Console.WriteLine(hero > monster ? "Hero wins!" : "Monster wins!");
```

This code is merely "*one possible solution*" because there are many different ways to perform the attack logic.

Regardless, your output should be similar to the following example output:

```Output
Monster was damaged and lost 1 health and now has 9 health.
Hero was damaged and lost 2 health and now has 8 health.
Monster was damaged and lost 1 health and now has 8 health.
Hero was damaged and lost 4 health and now has 4 health.
Monster was damaged and lost 7 health and now has 1 health.
Hero was damaged and lost 6 health and now has -2 health.
Monster wins!
```

If you were successful, congratulations! Continue on to the knowledge check in the next unit.

> [!IMPORTANT]
> If you had trouble completing this challenge, maybe you should review the previous units before you continue on. All new ideas we discuss in other modules will depend on your understanding of the ideas that were presented in this module.
