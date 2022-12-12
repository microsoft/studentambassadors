---
title: Knowledge check
durationInMinutes: 2
---

## quiz title: Check your knowledge

## Multiple Choice

Which technique should be **avoided** when changing a `string` value `4.123456789` into a `decimal`?
( ) `Convert.ToDecimal()` {{That's incorrect. Using `ToDecimal` is a valid technique.}}
( ) `decimal.TryParse()` {{That's incorrect. Using `TryParse` is a valid technique.}}
(x) `(decimal)` {{That's correct. You can't cast a `string` into a `decimal`.}}

## Multiple Choice

What type of action is changing a `float` into an `int`?
(x) This is a narrowing conversion. {{That's correct. Changing a `float` into an `int` is a narrowing conversion, because `float` can store more precision data than `int`.}}
( ) This is a widening conversion. {{That's incorrect. Changing a `float` into an `int` isn't a widening conversion because `float` can store more precision data than `int`.}}
( ) This is an illegal conversion. {{That's incorrect. Changing a `float` into an `int` isn't an illegal conversion. You can accomplish this, buy it's with the loss of precision data.}}
