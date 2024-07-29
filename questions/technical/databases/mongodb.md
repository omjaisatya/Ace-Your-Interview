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

## 16. What are the differences between MongoDB and a relational database?

**Answer:**

- **Schema:** MongoDB is schema-less, allowing for flexible document structures, whereas relational databases require a predefined schema.
- **Data Storage:** MongoDB stores data in BSON documents, while relational databases use tables with rows and columns.
- **Query Language:** MongoDB uses a query language based on JSON, while relational databases use SQL.
- **Scalability:** MongoDB supports horizontal scaling via sharding, while relational databases often use vertical scaling.

## 17. What is a BSON?

**Answer:**
BSON (Binary JSON) is a binary representation of JSON-like documents. It extends JSON’s capabilities by including additional data types, such as `Date` and `Binary`, and providing efficient serialization and deserialization.

## 18. Describe the purpose of the `$match` stage in the aggregation pipeline.

**Answer:**
The `$match` stage in the aggregation pipeline filters documents based on specified criteria, similar to a `find()` query. It only passes documents that meet the criteria to the next stage in the pipeline.

## 19. What is the purpose of the `$group` stage in the aggregation pipeline?

**Answer:**
The `$group` stage is used to group documents by a specified identifier and perform aggregation operations, such as counting, summing, or averaging. It helps in summarizing data across groups.

## 20. Explain the use of the `$lookup` stage in MongoDB.

**Answer:**
The `$lookup` stage performs a left outer join with another collection, allowing you to combine documents from different collections based on a matching field. It enables the aggregation of related data across collections.

## 21. What is the difference between `replaceOne()` and `updateOne()`?

**Answer:**

- **`replaceOne()`:** Replaces a single document that matches the query criteria with a new document. The entire document is replaced.
- **`updateOne()`:** Updates specific fields in a single document that matches the query criteria, leaving other fields unchanged.

## 22. How does MongoDB handle large objects, such as images or videos?

**Answer:**
MongoDB handles large objects using GridFS, a specification for storing and retrieving large files. GridFS divides the file into smaller chunks and stores them as separate documents in two collections: `fs.chunks` and `fs.files`.

## 23. What are MongoDB’s data consistency models?

**Answer:**
MongoDB offers several consistency models:

- **Read Concern:** Determines the level of isolation for read operations (e.g., `local`, `majority`).
- **Write Concern:** Specifies the level of acknowledgment requested from MongoDB for write operations (e.g., `w:1`, `w:majority`).

## 24. What is a MongoDB index type and give an example?

**Answer:**
MongoDB supports various index types, including:

- **Single Field Index:** Indexes a single field (e.g., `{ field: 1 }` for ascending order).
- **Compound Index:** Indexes multiple fields (e.g., `{ field1: 1, field2: -1 }` for ascending and descending order).
- **Text Index:** Enables text search on string fields (e.g., `{ field: "text" }`).
- **Geospatial Index:** Supports queries based on location data (e.g., `{ location: "2dsphere" }`).

## 25. How can you ensure that MongoDB is performant?

**Answer:**

- **Indexing:** Create indexes on frequently queried fields to improve query performance.
- **Sharding:** Distribute data across multiple servers to handle large datasets and high throughput.
- **Profiling:** Use MongoDB’s profiling tools to identify slow queries and optimize them.
- **Schema Design:** Design a schema that fits your access patterns and reduces the need for complex joins or aggregations.

## 26. What is a capped collection?

**Answer:**
A capped collection is a special type of MongoDB collection with a fixed size and automatically overwrites the oldest documents when it reaches its size limit. It maintains insertion order and is ideal for use cases like logs and caching.

## 27. What is the `$unwind` stage in the aggregation pipeline?

**Answer:**
The `$unwind` stage deconstructs an array field from the input documents to output a document for each element of the array. It is used to normalize data and perform operations on array elements.

## 28. Explain the concept of eventual consistency in MongoDB.

**Answer:**
Eventual consistency means that while data changes are propagated to all nodes in the replica set, there may be a delay before all nodes reflect the latest data. This model ensures high availability and performance but may result in temporary discrepancies.

## 29. What is the purpose of the `db.collection.stats()` command?

**Answer:**
The `db.collection.stats()` command provides detailed statistics about a collection, including document count, storage size, index size, and other performance metrics. It helps in analyzing and optimizing database performance.

## 30. Describe how you would model a one-to-many relationship in MongoDB.

**Answer:**
A one-to-many relationship can be modeled in MongoDB by embedding the "many" documents within the "one" document as an array. Alternatively, you can reference the "many" documents by storing their IDs in the "one" document and querying them separately.
