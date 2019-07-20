# `Array.prototype.difference` proposal

Find the difference between arrays by evaluating values from first array not included in the others.

## Motivation

Currently there is no way to evaluate the **difference** between two arrays which makes it difficult to compare two or more arrays.

The only way around is to iterate over each values and compare with the respective values in rest of the arrays, which is not a feasible task to do every time.

## Proposal

I propose the addition of a new method to the `Array` prototype - **`difference`**. This would give people a straight-forward way to compare arrays and check the difference. We will be  very useful in writing test cases' assertions and comparisions.

```js
[1, 'a', 3.14].difference([2, 'a', 3.145]) // returns [1, 3.14]
[1, null].difference([2, null]) // returns [1]
```

## Comparision to other languages

- Python has no general method but it's easy to write the comparision function - `array3 = [item for item in array1 if item not in array2]`
- Java even has no method but converting the array into a set and then removing the common items solves the problem
- In Ruby we can simple compare two arrays with *-* operator as `[1, 2] - [1, 3] // [2]`
- PHP has an in-built function which compares the values of two or more arrys - [`array-diff()`](https://www.php.net/manual/en/function.array-diff.php)

## Other Enhancements

- Can specify the depth upto which it should compare `Array.difference(Array, depth = 2)`
- Array caching can improve performance a lot
