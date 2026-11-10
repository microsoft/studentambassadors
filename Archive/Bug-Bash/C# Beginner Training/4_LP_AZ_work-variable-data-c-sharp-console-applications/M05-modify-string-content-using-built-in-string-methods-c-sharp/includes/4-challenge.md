---
title: Complete the challenge
durationInMinutes: 10
---

Code challenges throughout these modules will reinforce what you've learned and help you gain some confidence before continuing on.

## Challenge

In this challenge, you'll work with a string that contains a fragment of HTML. You'll extract data from the HTML fragment, replace some of its content, and remove other parts of its content to achieve the desired output.

### Step 1: Delete all of the code from the earlier exercise.

Delete or use the line comment operator // to comment out all of the code from the previous step.

### Step 2: Write code to extract data, replace data, and remove data from an input string.

Given the starting point in the following code listing, code to extract, replace, and remove portions of the `input`'s value to produce the desired output:

```c#
const string input = "<div><h2>Widgets &trade;</h2><span>5000</span></div>";

string quantity = "";
string output = "";

// Your work here

Console.WriteLine(quantity);
Console.WriteLine(output);
```

The following listing is the desired output once you've modified the code in the starting point.

```Output
Quantity: 5000
Output: <h2>Widgets &reg;</h2><span>5000</span>
```

You may only add code to the starting point code listing. You must not change the variable declarations. All of your work should go under the comment `// Your work here`.

You'll perform three operations on the input using the tools and techniques you learned in this module.

1. Set the `quantity` variable to the value you extract from between the `<span>` and `</span>` tags.
2. Set the `output` variable to the value of input, then remove the `<div>` and `</div>` tags.
3. Replace the HTML character `™` (`&trade;`) with `®` (`&reg`) in the `output` variable.

Whether you get stuck and need to peek at the solution or you finish successfully, continue on to view a solution to this challenge.

### Quick HTML primer

In case you're not familiar with HTML, it's the markup language that is used to create all web pages. This section can be skipped if you're already well versed in HTML. It's not designed to be a comprehensive tutorial, but provides enough information to complete this challenge.

In HTML, you define the structure of a document using tags. A tag is comprised of:

- an opening angle bracket `<`
- a closing angle bracket `>`
- a word describing the type of tag, so for example: `<div>`, `<span>`, `<h2>` etc.

Each tag has a corresponding closing tag that is indicated by a forward slash character `/`. So, if you see `<div>` there should be a corresponding `</div>` tag.

The content between the opening and closing tag is the content of that tag. The content can include text and other tags.

A set of tags can be embedded inside another set of tags. In fact, that is what gives an HTML document its hierarchical structure.
