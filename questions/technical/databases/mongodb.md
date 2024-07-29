# MongoDB Interview Questions

## 1. What is MongoDB?

**Answer:**
MongoDB is a NoSQL database designed for scalability and flexibility. It stores data in a format similar to JSON called BSON (Binary JSON), which allows for the storage of complex data structures and hierarchical data.

## 2. Explain the key features of MongoDB.

**Answer:**

- **Schema-less Design:** MongoDB does not require a predefined schema, allowing for flexible and dynamic data structures.
- **Document-Oriented Storage:** Data is stored in documents (BSON format), making it easier to model and retrieve complex data.
- **Scalability:** Supports horizontal scaling through sharding and vertical scaling through replica sets.
- **Indexing:** Provides rich indexing options to optimize query performance.
- **Aggregation Framework:** Allows for advanced data processing and analysis operations.
- **High Availability:** Ensured by replica sets, which provide automatic failover and data redundancy.

## 3. What is a document in MongoDB?

**Answer:**
In MongoDB, a document is a basic unit of data, stored in BSON format. It is analogous to a row in relational databases and can contain various data types, including nested structures and arrays.

## 4. What is a collection in MongoDB?

**Answer:**
A collection is a grouping of MongoDB documents, similar to a table in relational databases. Collections are schema-less and can store documents with different structures.

## 5. What is a replica set?

**Answer:**
A replica set is a group of MongoDB servers that maintain the same data set. Replica sets provide redundancy and high availability, as they automatically failover to a secondary node if the primary node fails.

## 6. How does sharding work in MongoDB?

**Answer:**
Sharding in MongoDB distributes data across multiple servers or shards to ensure horizontal scalability. Each shard contains a subset of the data, and the sharding key determines how data is distributed. MongoDB handles routing of queries and balancing of data across shards.

## 7. Explain the difference between `find()` and `findOne()`.

**Answer:**

- **`find()`:** Returns a cursor to all documents that match the query criteria. It can be used to retrieve multiple documents.
- **`findOne()`:** Returns a single document that matches the query criteria. It is typically used when only one document is expected.

## 8. What is an index in MongoDB?

**Answer:**
An index in MongoDB is a data structure that improves the speed of data retrieval operations. Indexes are created on fields to optimize query performance and support efficient data access.

## 9. How can you create an index in MongoDB?

**Answer:**
Indexes can be created using the `createIndex()` method. For example:

```javascript
db.collection.createIndex({ field: 1 });
```

## 10. What is the Aggregation Framework?

**Answer:**
The Aggregation Framework in MongoDB is a powerful tool for performing complex data processing and analysis operations. It allows for operations such as filtering, grouping, sorting, and projecting data using a pipeline of stages.

11. How do you handle transactions in MongoDB?
    Answer:
    MongoDB supports multi-document transactions, allowing for atomic operations across multiple documents and collections. Transactions are used to ensure data consistency and can be started, committed, or aborted using the `startSession()`, `commitTransaction()`, and `abortTransaction()` methods.

## 12. What are some common use cases for MongoDB?

**Answer:**
_Common use cases include:_

- **Content Management Systems:** For flexible and dynamic content storage.
- **Real-Time Analytics:** For processing and analyzing large volumes of data.
- **Internet of Things (IoT):** For storing and managing time-series data from various devices.
- **Catalogs:** For managing product or service catalogs with varying attributes.

## 13. What is the difference between `updateOne()` and `updateMany()`?

**Answer:**

- **`updateOne()`:** Updates a single document that matches the query criteria.
- **`updateMany()`:** Updates all documents that match the query criteria.

## 14. How can you ensure data integrity in MongoDB?

**Answer:**
_Data integrity can be ensured through:_

- **Schema Validation:** Define rules for document structure and content using validation schemas.
- **Transactions:** Use multi-document transactions for atomic operations.
- **Replica Sets:** Use replica sets for data redundancy and failover.

## 15. How do you backup and restore data in MongoDB?

**Answer:**

- **Backup:** Use the `mongodump` utility to create a backup of the MongoDB data.
- **Restore:** Use the `mongorestore` utility to restore data from a backup created by `mongodump`.
