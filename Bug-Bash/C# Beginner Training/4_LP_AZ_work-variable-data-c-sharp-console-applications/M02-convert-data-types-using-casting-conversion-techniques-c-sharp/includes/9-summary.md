---
title: Summary
durationInMinutes: 1
---

Our goal was to use several different techniques to change the data type of a given value.

We used *implicit conversion*, relying on the C# compiler to perform *widening conversions*. When the compiler was unable to perform an implicit conversion, we used *explicit conversions*. We used the `ToString()` method to explicitly convert a numeric data type into a `string`.

When we needed to perform `narrowing conversions`, we used several different techniques. We used the casting operator `()` when the conversion could be made safely and were willing to accept truncation of values after the decimal. And we used the `Convert()` method when we wanted to perform a conversion and use common rounding rules when performing a narrowing conversion.

Finally, we used the `TryParse()` methods when the conversion from a `string` to a numeric data type could potentially result in a data type conversion exception.

Without this wealth of options, it would be difficult to work in a strongly typed programming language. Fortunately, this well executed system of types, conversion, and casting can be harnessed to build error free applications.

## TODO: Add Ref links on C# types mapped to .NET types
[Casting and type conversions](https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/types/casting-and-type-conversions)
