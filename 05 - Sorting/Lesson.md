## `sort` and `limit` Methods

MongoDB offers two powerful methods for manipulating the results of your queries: `sort` and `limit`. Here's a summary of their functionalities:

**1. `sort` method:**

* **Purpose:** Orders the retrieved documents based on specified criteria.
* **Usage:**
    - As a query parameter:

    ```javascript
    db.collection.find({ /* query criteria */ }).sort({ /* sort criteria */ });
    ```

    - As part of the aggregation pipeline:

    ```javascript
    [{ $sort: { /* sort criteria */ } }]
    ```

* **Sort Criteria:**
    - Specify one or more fields and their corresponding sorting order (1 for ascending, -1 for descending).
    - Example: `sort({ "name": 1, "age": -1 })` (sorts by name ascending, then by age descending)
* **Indexes:** Using an appropriate index on the sorting fields can significantly improve performance.

**2. `limit` method:**

* **Purpose:** Limits the number of documents returned by a query.
* **Usage:**
    - As a query parameter:

    ```javascript
    db.collection.find({ /* query criteria */ }).limit(n);
    ```

    - As part of the aggregation pipeline:

    ```javascript
    [{ $limit: n }]
    ```

* **Parameter:** `n` (integer) representing the maximum number of documents to return.

**Combined Use:**

* You can chain `sort` and `limit` together to retrieve a specific number of documents in a desired order:

```javascript
db.collection.find({ /* query criteria */ }).sort({ /* sort criteria */ }).limit(n);
```

**Advantages:**

* Enhance user experience by presenting data in a specific order or displaying only a limited number of results per page.
* Improve query performance by leveraging indexes for sorting.

**Remember:**

* Sorting without an index can be resource-intensive, especially for large datasets.
* Choose appropriate sort criteria and limit values based on your specific needs.
