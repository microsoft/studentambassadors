The C# programming language is similar to any human written or spoken language inasmuch that you can choose different ways to express the same idea. Some words and phrases are more descriptive, accurate, or succinct than others. There are several ways to add branching logic in your application, and depending on the context, some are more expressive and succinct than others.

Suppose we wanted to add a feature to our application that displayed an employee's title at the company next to their name. However, since the title names change occasionally, we only store the employee's level, which is a numeric equivalent of their title.

When we want to display their title, we would need to evaluate the numeric level and return the title.

There are several levels and matching titles. Occasionally, the company adds new levels and titles. If this happens before we can update our application, we need to use a generic title "Associate" until we can update our software.

In this scenario, we could easily use an `if-elseif-else` branching construct. But if there are many possible levels and titles, the `switch` statement might be easier to read, understand, and modify.

In this module, you'll use the `switch-case` construct to add branching logic where you must match one variable or expression against many possible values.

By the end of this module, you'll be able to build simple applications that can accept user input, combine that input with literal text, and output the result to the user.

## Learning objectives

In this module, you will:

- Use the `switch-case` construct to match a variable or expression against several possible outcomes.
- Convert code that uses an `if-elseif-else` construct into a `switch-case` construct.

## Prerequisites:

- Experience using the `if-elseif-else` construct for adding branching logic
- Experience working with variables, string interpolation, and printing output