## Updating Documents in MongoDB:

**1. `updateOne` Method:**

* Updates a single document matching the specified query criteria.
* Takes three arguments:
    * **Query:** Defines the document(s) to be updated.
    * **Update document:** Specifies the changes to be applied. Uses update operators like `$set`, `$inc`, `$unset`, etc.
    * **Options (optional):** Additional options like `upsert` (create a new document if no match is found) can be used.

**Example:**

```javascript
db.collection.updateOne({ _id: ObjectId("12345") }, { $set: { "name": "Alice Doe" } });
```

This updates the document with `_id` "12345" by setting the "name" field to "Alice Doe".

**2. `updateMany` Method:**

* Updates multiple documents that match the specified query criteria.
* Similar to `updateOne`, but updates all matching documents.

**Example:**

```javascript
db.collection.updateMany({ age: { $gt: 25 } }, { $inc: { age: 1 } });
```

This increments the "age" field by 1 for all documents where "age" is greater than 25.

**3. `replaceOne` Method:**

* Replaces an entire document matching the specified query criteria with a new document.
* Takes two arguments:
    * **Query:** Defines the document to be replaced.
    * **Replacement document:** The new document that will replace the existing one.

**Example:**

```javascript
db.collection.replaceOne({ _id: ObjectId("56789") }, { name: "John Doe", age: 30 });
```

This replaces the document with `_id` "56789" with a new document containing the specified name and age.

**Important Points:**

* By default, `updateOne` and `updateMany` update documents in-place. If you prefer to return the modified document, use the `findOneAndUpdate` or `updateMany` variants with the `returnDocument` option.
* Choose the appropriate method based on your need to update one or multiple documents.
* Leverage update operators for efficient and concise updates to specific fields within documents.

**Update Operators:**

These operators allow you to perform specific modifications on fields within documents:

* **`$set`:** Sets the value of a field.

```javascript
db.collection.updateOne({ _id: 1 }, { $set: { "name": "Alice Doe" } }); // Sets "name" to "Alice Doe"
```

* **`$unset`:** Removes a field from a document.

```javascript
db.collection.updateOne({ _id: 1 }, { $unset: { "age": 1 } }); // Removes the "age" field
```

* **`$inc`:** Increments the numeric value of a field.

```javascript
db.collection.updateOne({ _id: 1 }, { $inc: { "count": 1 } }); // Increments "count" by 1
```

* **`$dec`:** Decrements the numeric value of a field.

```javascript
db.collection.updateOne({ _id: 1 }, { $dec: { "stock": 2 } }); // Decrements "stock" by 2
```

* **`$push`:** Appends a value to an array field.

```javascript
db.collection.updateOne({ _id: 1 }, { $push: { "interests": "hiking" } }); // Adds "hiking" to the "interests" array
```

* **`$pull`:** Removes a value from an array field.

```javascript
db.collection.updateOne({ _id: 1 }, { $pull: { "interests": "reading" } }); // Removes "reading" from the "interests" array
```

* **`$rename`:** Renames a field.

```javascript
db.collection.updateOne({ _id: 1 }, { $rename: { "oldName": "newName" } }); // Renames "oldName" to "newName"
```

**Useful Commands:**
```javascript
db.[collection-name].updateOne({filter},{update}) # use FILTER to find (retrieve) the document you want to update and the UPDATE specify the changes you want to make.
db.[collection-name].updateMany({filter},{update})
```