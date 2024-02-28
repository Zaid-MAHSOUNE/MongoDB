## Operators:

**1. Comparison Operators:**

* Used to compare values and filter documents based on the comparison result.
* Commonly used operators include:
    * `$eq`: Checks for equality (e.g., `{ "age": { $eq: 30 } }`).
    * `$ne`: Checks if not equal (e.g., `{ "balance": { $ne: 0 } }`).
    * `$gt`: Checks if greater than (e.g., `{ "price": { $gt: 10 } }`).
    * `$gte`: Checks if greater than or equal to (e.g., `{ "rating": { $gte: 4 } }`).
    * `$lt`: Checks if less than (e.g., `{ "stock": { $lt: 5 } }`).
    * `$lte`: Checks if less than or equal to (e.g., `{ "balance": { $lte: 0 } }`).
    * `$in`: Checks if include in array (e.g., `{ age: { $in: [25, 30, 35] } }`).


**2. Logical Operators:**

* Combine multiple conditions for complex filtering.
* Commonly used operators include:
    * `$and`: Filters documents that satisfy all specified conditions (e.g., `{ $and: [{ "age": { $gt: 21 } }, { "active": true }] }`).
    * `$or`: Filters documents that satisfy at least one of the specified conditions (e.g., `{ $or: [{ "name": "Alice" }, { "city": "New York" }] }`).
    * `$not`: Inverts the result of a condition (e.g., `{ "verified": { $not: true } }`).

**3. Array Operators:**

* Used to work with and manipulate arrays within documents.
* Commonly used operators include:
    * `$push`: Adds an element to the end of an array (e.g., `{ $push: { "cart": "item3" } }`).
    * `$pop`: Removes the first or last element from an array (e.g., `{ $pop: { "history": -1 } }` removes the last element).
    * `$pull`: Removes all occurrences of a specific value from an array (e.g., `{ $pull: { "tags": "removedTag" } }`).

**4. Update Operators:**

* Used to modify specific fields within existing documents.
* Commonly used operators include:
    * `$set`: Sets the value of a field (e.g., `{ $set: { "name": "John Doe" } }`).
    * `$unset`: Removes a field from a document (e.g., `{ $unset: { "temporaryData": 1 } }`).
    * `$inc`: Increments the value of a numeric field (e.g., `{ $inc: { "count": 1 } }`).
    * `$dec`: Decrements the value of a numeric field (e.g., `{ $dec: { "stock": 2 } }`).

**5. Projection Operator:**

* Used to specify which fields to include or exclude when retrieving documents.
* Example: `{ "name": 1, "age": 0 }` includes "name" and excludes "age" fields.

**Remember:**

* This is just a selection of important operators.
* Refer to the official documentation for a comprehensive list and detailed explanations: [https://www.mongodb.com/docs/manual/reference/operator/](https://www.mongodb.com/docs/manual/reference/operator)