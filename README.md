# MONGOCHEETSHEET
THIS IS TO CLEAR YOUR SYNTACTICAL SUGAR

Here's a simple and well-organized MongoDB cheat sheet with key commands, designed to be easy to understand:

### MongoDB Cheat Sheet

#### 1. **Basic Commands**
- **Show all databases**  
  ```bash
  show dbs
  ```
  This lists all the databases in MongoDB.

- **Use a specific database**  
  ```bash
  use <database_name>
  ```
  Switches to the given database. If it doesn’t exist, MongoDB will create it when data is inserted.

- **Show all collections in a database**  
  ```bash
  show collections
  ```
  Lists all collections (like tables in SQL) in the current database.

#### 2. **Insert Data**
- **Insert one document**  
  ```javascript
  db.<collection_name>.insertOne({ key1: "value1", key2: "value2" })
  ```
  Example:  
  ```javascript
  db.movies.insertOne({ title: "Inception", director: "Christopher Nolan" })
  ```

- **Insert multiple documents**  
  ```javascript
  db.<collection_name>.insertMany([{ key1: "value1" }, { key2: "value2" }])
  ```

#### 3. **Query Data (Find)**  
- **Find all documents in a collection**  
  ```javascript
  db.<collection_name>.find()
  ```
  Example:  
  ```javascript
  db.movies.find()
  ```

- **Find documents with a specific condition**  
  ```javascript
  db.<collection_name>.find({ key: "value" })
  ```
  Example:  
  ```javascript
  db.movies.find({ director: "Christopher Nolan" })
  ```

- **Find one document**  
  ```javascript
  db.<collection_name>.findOne({ key: "value" })
  ```

#### 4. **Update Data**
- **Update one document**  
  ```javascript
  db.<collection_name>.updateOne({ key: "value" }, { $set: { key: "new_value" } })
  ```
  Example:  
  ```javascript
  db.movies.updateOne({ title: "Inception" }, { $set: { director: "Nolan" } })
  ```

- **Update multiple documents**  
  ```javascript
  db.<collection_name>.updateMany({ key: "value" }, { $set: { key: "new_value" } })
  ```

#### 5. **Delete Data**
- **Delete one document**  
  ```javascript
  db.<collection_name>.deleteOne({ key: "value" })
  ```

- **Delete multiple documents**  
  ```javascript
  db.<collection_name>.deleteMany({ key: "value" })
  ```

#### 6. **Aggregation (Advanced Querying)**
- **Simple aggregation (e.g., count documents)**  
  ```javascript
  db.<collection_name>.countDocuments({ key: "value" })
  ```

- **Group documents and calculate**  
  ```javascript
  db.<collection_name>.aggregate([
    { $group: { _id: "$key", total: { $sum: 1 } } }
  ])
  ```

#### 7. **Indexing (Optimize Queries)**
- **Create an index on a field**  
  ```javascript
  db.<collection_name>.createIndex({ key: 1 })
  ```
  Example:  
  ```javascript
  db.movies.createIndex({ title: 1 })
  ```

#### 8. **Common Operators**
- **Comparison operators**:  
  - `$eq`: Equal to  
    ```javascript
    db.movies.find({ rating: { $eq: 9 } })
    ```
  - `$gt`: Greater than  
    ```javascript
    db.movies.find({ rating: { $gt: 8 } })
    ```
  - `$lt`: Less than  
    ```javascript
    db.movies.find({ rating: { $lt: 5 } })
    ```

- **Logical operators**:  
  - `$and`: AND condition  
    ```javascript
    db.movies.find({ $and: [{ director: "Nolan" }, { rating: { $gt: 8 } }] })
    ```
  - `$or`: OR condition  
    ```javascript
    db.movies.find({ $or: [{ rating: 9 }, { rating: 10 }] })
    ```

---

This should give you a solid foundation for working with MongoDB. If you need any more examples or want to dive deeper into specific queries, feel free to ask!
