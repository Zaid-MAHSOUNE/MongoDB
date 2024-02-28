## Deleting Documents in MongoDB:
**Methods:**

* **`deleteOne()`:** Removes **one** document that matches the specified query criteria.
* **`deleteMany()`:** Removes **all** documents that match the specified query criteria.
* **`dropCollection()`:** Drops an entire collection, removing **all** documents within it.

**Query Criteria:**

Each delete method takes a query document as an argument, specifying the documents to be removed. You can use various operators like comparison operators, logical operators, and field existence checks to define the selection criteria. For example:

```javascript
// Delete the document with _id of "12345"
db.collection.deleteOne({ _id: ObjectId("12345") });

// Delete all documents where age is greater than 25
db.collection.deleteMany({ age: { $gt: 25 } });
```

**Important Considerations:**

* Deleted documents are **permanent** and cannot be recovered without backups.
* Use caution when deleting documents, especially with `deleteMany`, as it removes all matching documents.
* Consider using `find` before deletion to preview the documents that will be affected.

**Additional Options:**

* Both `deleteOne` and `deleteMany` offer optional arguments for customization:
    * `bypassDocumentValidation`: Skips document validation (use with caution).
    * `collation`: Specifies a custom collation for string comparisons.

**Further Learning:**

For detailed explanations, examples, and advanced deletion functionalities, refer to the official MongoDB documentation: [https://www.mongodb.com/docs/manual/tutorial/remove-documents/](https://www.mongodb.com/docs/manual/tutorial/remove-documents/)

**Remember:** Deleting documents should be done with intention and understanding to maintain data integrity within your MongoDB collections.

**Useful Commands:**
```javascript
db.[collection-name].deleteOne({query}) # QUERY to select the document that you want to delete
```