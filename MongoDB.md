# Top 50 MongoDB Questions for MERN Stack Developers (WorkElate)

## Basics

1. **What is MongoDB?**  
   MongoDB is a NoSQL, document-oriented database that stores data in flexible, JSON-like documents.

2. **How does MongoDB store data?**  
   In BSON (Binary JSON) format as documents inside collections.

3. **What is a Collection in MongoDB?**  
   A group of related documents, similar to a table in relational databases.

4. **What is a Document in MongoDB?**  
   A JSON-like object containing key-value pairs, like a record.

5. **Difference between MongoDB and SQL?**  
   MongoDB is schema-less and stores JSON documents; SQL uses structured tables and schemas.

6. **How do you connect MongoDB in Node.js?**  
   Using `mongoose.connect('mongodb://localhost:27017/dbname')`.

7. **What is Mongoose?**  
   An ODM (Object Data Modeling) library to interact with MongoDB in Node.js.

8. **Why use Mongoose over native MongoDB driver?**  
   Mongoose provides schema, validation, middleware, and cleaner queries.

9. **How do you define a schema in Mongoose?**  
   ```js
   const UserSchema = new mongoose.Schema({ name: String, email: String });
````

10. **How to create a model from a schema?**

    ```js
    const User = mongoose.model('User', UserSchema);
    ```

---

## CRUD Operations

11. **How to create a document?**

    ```js
    await User.create({ name: 'John' });
    ```

12. **How to read all documents?**

    ```js
    const users = await User.find();
    ```

13. **How to find one document by ID?**

    ```js
    const user = await User.findById(id);
    ```

14. **How to update a document?**

    ```js
    await User.findByIdAndUpdate(id, { name: 'Updated' });
    ```

15. **How to delete a document?**

    ```js
    await User.findByIdAndDelete(id);
    ```

16. **How to use `.save()` in Mongoose?**

    ```js
    const user = new User({ name: 'Tom' });
    await user.save();
    ```

17. **How to filter documents with conditions?**

    ```js
    const users = await User.find({ age: { $gt: 20 } });
    ```

18. **How to sort results?**

    ```js
    const users = await User.find().sort({ name: 1 });
    ```

19. **How to limit results?**

    ```js
    const users = await User.find().limit(10);
    ```

20. **How to paginate results?**

    ```js
    const users = await User.find().skip(10).limit(10);
    ```

---

## Schema & Validation

21. **How to add validation in schema?**

    ```js
    name: { type: String, required: true }
    ```

22. **How to define default values?**

    ```js
    createdAt: { type: Date, default: Date.now }
    ```

23. **What is unique constraint in Mongoose?**
    Ensures no duplicate values.

    ```js
    email: { type: String, unique: true }
    ```

24. **What is enum in schema?**
    Limits values to a set:

    ```js
    role: { type: String, enum: ['admin', 'user'] }
    ```

25. **What is a virtual field?**
    A computed field not stored in DB.

    ```js
    schema.virtual('fullName').get(() => this.fname + ' ' + this.lname);
    ```

---

## Aggregation & Querying

26. **What is aggregation in MongoDB?**
    A framework for transforming data using pipelines like `$match`, `$group`.

27. **How to use aggregation in Mongoose?**

    ```js
    Model.aggregate([{ $group: { _id: "$role", count: { $sum: 1 } } }]);
    ```

28. **What is `$match` in aggregation?**
    Filters documents.

    ```js
    { $match: { age: { $gt: 20 } } }
    ```

29. **What is `$group` in aggregation?**
    Groups documents by a field and performs operations like `$sum`, `$avg`.

30. **How to perform text search?**

    ```js
    Model.find({ $text: { $search: "keyword" } });
    ```

---

## Relationships

31. **What is referencing in MongoDB?**
    Linking documents using `_id`.

    ```js
    post: { type: mongoose.Schema.Types.ObjectId, ref: 'Post' }
    ```

32. **How to populate referenced data?**

    ```js
    User.find().populate('posts');
    ```

33. **Difference between embedding and referencing?**

    * Embedding: Store related data in one document.
    * Referencing: Link documents via ID.

34. **When to embed vs reference?**
    Embed for tightly coupled data (like comments); reference for loosely coupled (user-post).

35. **What is `populate()` in Mongoose?**
    Replaces ObjectId with actual referenced document.

---

## Indexing & Performance

36. **How to create an index?**

    ```js
    schema.index({ email: 1 });
    ```

37. **How to check indexes on a collection?**

    ```js
    db.users.getIndexes()
    ```

38. **What is compound index?**
    Index on multiple fields.

    ```js
    schema.index({ name: 1, age: -1 });
    ```

39. **What is TTL index?**
    Index that deletes documents after a time.

    ```js
    schema.index({ createdAt: 1 }, { expireAfterSeconds: 3600 });
    ```

40. **How to avoid performance issues in MongoDB?**
    Use indexes, limit embedding, use lean queries, and paginate data.

---

## Deployment & Tools

41. **What is MongoDB Atlas?**
    A cloud-based MongoDB service.

42. **How to connect MongoDB Atlas in Node.js?**
    Use the connection string provided by Atlas in `mongoose.connect()`.

43. **How to secure MongoDB?**
    Use environment variables, strong passwords, and IP whitelisting.

44. **How to backup MongoDB?**
    Use `mongodump` for local or Atlas backup for cloud.

45. **What is MongoDB Compass?**
    GUI tool to visualize and interact with MongoDB data.

---

## Real-time & Advanced

46. **How to make real-time updates in MERN stack?**
    Use MongoDB change streams with WebSocket/Socket.io.

47. **What is Change Stream in MongoDB?**
    A feature to listen to real-time changes in collections.

48. **How to use `.lean()` in Mongoose?**
    Returns plain JS objects instead of Mongoose documents.

    ```js
    await User.find().lean();
    ```

49. **How to handle MongoDB connection errors?**
    Use try/catch and listen for connection events.

50. **Best practices for MongoDB in production?**

    * Use indexes
    * Optimize queries
    * Secure access
    * Monitor performance
    * Avoid large embedded documents

```
