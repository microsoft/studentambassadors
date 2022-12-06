The following code is one possible solution for the challenge from the previous unit.

```c#
for (int i = 1; i < 101; i++)
{
    if ((i % 3 == 0) && (i % 5 == 0))
        Console.WriteLine($"{i} - FizzBuzz");
    else if (i % 3 == 0)
        Console.WriteLine($"{i} - Fizz");
    else if (i % 5 == 0)
        Console.WriteLine($"{i} - Buzz");
    else
        Console.WriteLine($"{i}");
}
```

This code is merely "*one possible solution*".

The `for` statement is important because it allows you to iterate through the code block 100 times.

The `if-elseif-else` allows you to check for the divisors of 3 and 5.

The `%`, the mod operator, allows you to determine if 3 or 5 divide into another number without a remainder.

And the `&&` operator ensures that a number can be divided into both 3 and 5 for the `FizzBuzz` condition.

The code should produce the following output from 1 to 100.

```Output
1
2
3 - Fizz
4
5 - Buzz
6 - Fizz
7
8
9 - Fizz
10 - Buzz
11
12 - Fizz
13
14
15 - FizzBuzz
16
17
18 - Fizz
19
20 - Buzz
21 - Fizz
22
23
24 - Fizz
25 - Buzz
26
27 - Fizz
28
29
30 - FizzBuzz
31
32
33 - Fizz
34
35 - Buzz
36 - Fizz
37
38
39 - Fizz
40 - Buzz
41
42 - Fizz
43
44
45 - FizzBuzz
46
47
48 - Fizz
49
50 - Buzz
51 - Fizz
52
53
54 - Fizz
55 - Buzz
56
57 - Fizz
58
59
60 - FizzBuzz
61
62
63 - Fizz
64
65 - Buzz
66 - Fizz
67
68
69 - Fizz
70 - Buzz
71
72 - Fizz
73
74
75 - FizzBuzz
76
77
78 - Fizz
79
80 - Buzz
81 - Fizz
82
83
84 - Fizz
85 - Buzz
86
87 - Fizz
88
89
90 - FizzBuzz
91
92
93 - Fizz
94
95 - Buzz
96 - Fizz
97
98
99 - Fizz
100 - Buzz
```

If you were successful, congratulations! Continue on to the knowledge check in the next unit.

> [!IMPORTANT]
> If you had trouble completing this challenge, maybe you should review the previous units before you continue on. All new ideas we discuss in other modules will depend on your understanding of the ideas that were presented in this module.
