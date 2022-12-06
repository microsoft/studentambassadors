---
title:   Summary
durationInMinutes: 3
---
In our scenario, we needed to work with a sequence of Order IDs programmatically to identify potentially fraudulent orders. We created an array of Order IDs, then iterated through each element of the sequence looking for a common fraud trait.

C# Arrays allowed us to store each Order ID as an element of an array. We addressed a specific element of the array using an index -- a zero-based numeric value. We could retrieve and set the value in each element. We iterated through the elements of the array to inspect or output each element's value.

Imagine how difficult it would be to handle related data in our code if we *didn't* have a structure like an array? We would need to know ahead of time just how many data elements we expected to work with and define a separate variable for each value. That would create a brittle solution.

Arrays can be sized when created according to the amount of data we need to work with. In other modules, you'll learn how to add or remove the number of elements from arrays at run time. You'll learn how to sort, filter, query, and aggregate values in arrays. You'll learn how to split a string into an array based on some delimiter. As you get even more familiar with arrays (and similar data structures), you'll use them frequently when you need to flexibly work with data in your applications.
