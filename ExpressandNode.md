# Top 50 Express & Node.js Questions for MERN Stack Developers (WorkElate)

## 📌 Basics

1. **What is Node.js?**  
   Node.js is a runtime environment that lets you run JavaScript on the server side using the V8 engine.

2. **What is Express.js?**  
   Express is a fast and minimal Node.js web framework used to build APIs and web applications.

3. **Why use Express with Node.js?**  
   It simplifies routing, middleware management, and request handling.

4. **How do you initialize a Node.js project?**  
   `npm init` or `npm init -y`

5. **How to install Express?**  
   `npm install express`

---

## 📁 File Structure & Setup

6. **Basic Express server setup:**  
   ```js
   const express = require('express');
   const app = express();
   app.listen(3000, () => console.log("Server running"));
````

7. **How to serve static files?**

   ```js
   app.use(express.static('public'));
   ```

8. **How to structure Express project?**

   * `routes/`
   * `controllers/`
   * `models/`
   * `middlewares/`
   * `app.js` or `server.js`

9. **How to read `.env` files in Node.js?**
   Install `dotenv` and use:

   ```js
   require('dotenv').config();
   ```

10. **Where should routes be defined?**
    In separate `routes/` files, then imported into `app.js`.

---

## 🌐 Routing

11. **Define a GET route:**

    ```js
    app.get('/users', (req, res) => res.send('Users List'));
    ```

12. **POST route example:**

    ```js
    app.post('/login', (req, res) => {});
    ```

13. **Route with URL parameters:**

    ```js
    app.get('/user/:id', (req, res) => res.send(req.params.id));
    ```

14. **How to use query parameters?**

    ```js
    req.query.name
    ```

15. **What is `req.body` used for?**
    To access data from POST requests.

---

## 🧩 Middleware

16. **What is middleware in Express?**
    Functions that run before route handlers to modify requests or responses.

17. **Example of middleware:**

    ```js
    app.use((req, res, next) => {
      console.log('Time:', Date.now());
      next();
    });
    ```

18. **How to use `express.json()`?**

    ```js
    app.use(express.json());
    ```

19. **Third-party middleware example?**

    ```js
    const cors = require('cors');
    app.use(cors());
    ```

20. **Route-specific middleware example:**

    ```js
    app.get('/admin', authMiddleware, (req, res) => {});
    ```

---

## 🔐 Authentication & Security

21. **How to hash passwords in Node.js?**
    Use `bcrypt`:

    ```js
    const bcrypt = require('bcryptjs');
    const hashed = await bcrypt.hash(password, 10);
    ```

22. **How to generate JWT tokens?**

    ```js
    const jwt = require('jsonwebtoken');
    const token = jwt.sign({ id }, 'secretKey');
    ```

23. **How to protect routes using JWT?**
    Use a middleware to verify `req.headers.authorization`.

24. **How to use Helmet in Express?**

    ```js
    const helmet = require('helmet');
    app.use(helmet());
    ```

25. **How to enable CORS in Express?**

    ```js
    const cors = require('cors');
    app.use(cors());
    ```

---

## 📦 Modules & Packages

26. **How to import modules in Node.js?**

    ```js
    const fs = require('fs');
    ```

27. **Difference between CommonJS and ES Modules?**
    CommonJS uses `require`, ESModules use `import/export`.

28. **How to create a custom module?**

    ```js
    module.exports = function() { ... }
    ```

29. **What is nodemon?**
    Tool that restarts the server automatically on file changes.

30. **How to install nodemon?**
    `npm install -g nodemon` or as dev dependency.

---

## 📂 File System & API Integration

31. **How to read/write files in Node.js?**

    ```js
    fs.readFile('file.txt', callback);
    fs.writeFile('file.txt', 'Hello', callback);
    ```

32. **How to call external API in Node.js?**
    Use `axios` or `node-fetch`:

    ```js
    const axios = require('axios');
    const data = await axios.get('https://api.com');
    ```

33. **How to handle file uploads in Express?**
    Use `multer` middleware.

34. **How to use Multer for image uploads?**

    ```js
    const upload = multer({ dest: 'uploads/' });
    app.post('/upload', upload.single('image'), ...);
    ```

35. **How to send JSON response?**
    `res.json({ message: "Success" });`

---

## 🛠️ Error Handling & Debugging

36. **How to handle errors globally?**
    Define an error-handling middleware:

    ```js
    app.use((err, req, res, next) => {
      res.status(500).json({ error: err.message });
    });
    ```

37. **How to throw a custom error?**
    `throw new Error("Custom error");`

38. **How to handle 404 routes?**

    ```js
    app.use((req, res) => res.status(404).send('Not Found'));
    ```

39. **How to debug Node.js?**
    Use `console.log()`, or VS Code’s debugger.

40. **How to handle async/await errors?**
    Use `try/catch` or pass error to `next(err)`.

---

## 🧪 Testing & Deployment

41. **How to test Express routes?**
    Use tools like `Jest`, `Supertest`, or `Mocha`.

42. **How to deploy Node.js app?**

    * Use platforms like Render, Railway, or VPS
    * Set `PORT` in `.env`
    * Run: `node app.js`

43. **How to use `process.env.PORT`?**

    ```js
    const PORT = process.env.PORT || 3000;
    ```

44. **What is a build script in Node.js?**
    A script defined in `package.json` to start/prepare the app.

45. **What is PM2 in Node.js?**
    Production process manager for keeping apps alive.

---

## 📚 Advanced Topics

46. **What is async/await in Node.js?**
    Syntactic sugar for promises, used for cleaner asynchronous code.

47. **How does the event loop work in Node.js?**
    It processes async tasks using callbacks in phases (timers, I/O, etc.).

48. **How to create a REST API in Express?**
    Define routes for CRUD (GET, POST, PUT, DELETE) for a resource.

49. **What is clustering in Node.js?**
    Running multiple Node.js processes to handle load using `cluster` module.

50. **What is middleware chaining?**
    Multiple middlewares can run in order using `next()`.

```
