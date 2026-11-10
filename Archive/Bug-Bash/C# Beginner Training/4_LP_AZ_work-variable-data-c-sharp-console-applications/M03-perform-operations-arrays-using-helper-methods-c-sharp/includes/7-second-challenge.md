---
title: Complete the second challenge
durationInMinutes: 5
---

Previously, we set out to write code that would store Order IDs belonging to potentially fraudulent orders. We hope to find those fraudulent orders as early as possible and flag them for deeper analysis.

Our team found a pattern -- orders that start with the letter "B" encounter fraud 25 times the normal rate. Our job is to write new code that will output the Order ID of new orders where the Order ID starts with the letter "B". This will be used by our fraud team to investigate further.

Using the code below as a starting point, you'll need to parse Order IDs out of a string containing a sequence of incoming orders (the `orderStream`). Then, you'll print each Order ID that starts with the letter "B".

```c#
string orderStream = "B123,C234,A345,C15,B177,G3003,C235,B179";

// Your code here
```

The output should match the following output:

```Output
B123
B177
B179

```

> [!IMPORTANT]
> Here's a hint: As you loop through each element in your array, you'll need a decision statement. The decision statement will need to use a method on the string class to determine if a string starts with a specific letter. If you need help, you may want to review other modules in this learning path.

Whether you get stuck and need to peek at the solution or you finish successfully, continue on to view a solution to this challenge.