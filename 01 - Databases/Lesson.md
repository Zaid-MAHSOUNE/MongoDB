## Databases :

## Databases and Collections

In MongoDB, data is organized into a hierarchical structure similar to filing cabinets:

**Databases:**

* Represent the **top level**, acting like **cabinets** within a filing system.
* Each database holds a distinct **namespace** for your data and can contain multiple collections.
* Think of them as separate departments within a company, each managing its own data.

**Collections:**

* Reside **within** a database, similar to **drawers** within a cabinet.
* Group documents that share a similar **schema** (structure) or purpose.
* They're analogous to tables in relational databases, but with more flexibility.
* Each collection can have a **different schema** within a single database.

**Key Points:**

* **Independence:** Unlike relational databases, databases in MongoDB are **independent** and don't require predefined relationships with other databases.
* **Scalability:** Databases can be **scaled horizontally** by adding more shards (data partitions) on multiple servers, improving performance and capacity.
* **Management:** You can use tools or the command-line interface (CLI) to **create, drop (delete), list, and rename databases**.

**Useful Commands:**

- To show available databases :
```bash
  show dbs
```
- To use (create) a database :
```bash
  use [db-name]  
``` 
- To add a collection :
```bash
  db.createCollection("[db-name]")  
```
- To drop a the in use database :
```bash
  db.dropDatabase()   
```
