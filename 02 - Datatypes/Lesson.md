
**Primitive Types:**

* **String:** Textual data. Example: `"name": "Alice"`
* **Number:** Integers (whole numbers) or floating-point numbers (decimals). Examples: `42`, `3.14`
* **Boolean:** True or false values. Examples: `true`, `false`
* **Null:** Absence of a value. Example: `"age": null` (age unknown)
* **ObjectId:** Unique 12-byte identifier generated for documents. Example: `ObjectId("5ebd22eec6932ca2061d1234")`
* **Date/Time:** Represents date and time values. Examples: `ISODate("2024-02-26T19:15:00Z")`, `new Date()` (current timestamp)

**Complex Types:**

* **Array:** Ordered collection of values of any data type. Example: `"interests": ["reading", "hiking", "coding"]`
* **Object:** Stores key-value pairs (key: string, value: any data type). Allows nested structures. Example:

```json
{
  "name": "John Doe",
  "address": {
    "street": "123 Main St",
    "city": "Anytown",
    "state": "CA"
  }
}
```

**Additional Points:**

* **Flexibility:** Mix and match data types within a document as needed.
* **Extended Types:** BSON offers additional types like binary data and regular expressions.
* **Optimization:** Choose data types appropriate for your data to improve storage and query performance.

