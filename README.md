# MongoDB $inc Operator Error with String Value
This example demonstrates an incorrect usage of the `$inc` operator in MongoDB update operations. The `$inc` operator is used to increment a numerical field by a specified value. Attempting to increment a field with a non-numerical value results in an error.

## Bug
The following code snippet demonstrates the bug: attempting to increment a field named `count` by the string value `'abc'`.

```javascript
// Incorrect usage of $inc operator
db.collection('myCollection').updateOne({ _id: 1 }, { $inc: { count: 'abc' } });
```

## Solution
The solution involves ensuring that the value passed to the `$inc` operator is a number. Here's the corrected code:

```javascript
db.collection('myCollection').updateOne({ _id: 1 }, { $inc: { count: 1 } });
```