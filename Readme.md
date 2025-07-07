# 🔥 Top 50 MERN Stack Interview Questions & Answers (WorkElate)

---

## ✅ 1–10: MERN Stack Basics

1. **What is MERN Stack?**  
   MERN stands for MongoDB, Express.js, React.js, and Node.js — a full-stack JavaScript solution.

2. **Why choose MERN Stack?**  
   Uses JavaScript end-to-end, fast development, scalable, and has strong community support.

3. **What is the flow of a MERN application?**  
   React (Frontend) → Express + Node (Backend) → MongoDB (Database)

4. **Which part handles the frontend in MERN?**  
   React.js

5. **Which part is responsible for the backend API?**  
   Node.js with Express.js

6. **How is data stored in MERN?**  
   In MongoDB as JSON-like documents (BSON format).

7. **What is the role of Express in MERN?**  
   Express handles routing and middleware logic on the server.

8. **What is the role of Node.js in MERN?**  
   Executes JavaScript server-side and hosts the backend.

9. **What is the role of React in MERN?**  
   Builds interactive and component-based user interfaces.

10. **What is the role of MongoDB in MERN?**  
    Stores application data in NoSQL format.

---

## ⚙️ 11–20: MongoDB & Mongoose

11. **How to define a MongoDB schema using Mongoose?**  
    ```js
    const UserSchema = new mongoose.Schema({ name: String });
    ```

12. **How to connect MongoDB in Node.js?**  
    ```js
    mongoose.connect('mongodb://localhost:27017/mydb');
    ```

13. **What is a model in Mongoose?**  
    A model represents a MongoDB collection and allows querying documents.

14. **How to perform a read operation?**  
    ```js
    User.find()
    ```

15. **How to perform a write operation?**  
    ```js
    const user = new User({ name: 'Sandeep' });
    await user.save();
    ```

16. **How to handle MongoDB errors?**  
    Use `try/catch` and log or send error messages.

17. **What is populate in Mongoose?**  
    Populates referenced fields from other collections.

18. **How to filter documents with conditions?**  
    ```js
    User.find({ age: { $gt: 18 } })
    ```

19. **What is the use of indexes in MongoDB?**  
    Improve query performance.

20. **How does MongoDB differ from SQL databases?**  
    No fixed schema, stores documents instead of rows.

---

## 🌐 21–30: Express.js & Node.js

21. **How to set up an Express server?**  
    ```js
    const express = require('express');
    const app = express();
    app.listen(3000);
    ```

22. **How to create routes in Express?**  
    ```js
    app.get('/api', (req, res) => res.send('Hello'));
    ```

23. **How to parse JSON in requests?**  
    Use: `app.use(express.json())`

24. **How to handle errors in Express?**  
    Create an error-handling middleware:
    ```js
    app.use((err, req, res, next) => res.status(500).send(err.message));
    ```

25. **What is middleware in Express?**  
    Functions that process requests before reaching the route handler.

26. **How to create modular routes?**  
    Use `express.Router()` in separate route files.

27. **How does Express communicate with MongoDB?**  
    Through Mongoose or the MongoDB native driver.

28. **How to handle file uploads in Express?**  
    Use `multer` middleware.

29. **How to secure Express apps?**  
    Use `helmet`, `cors`, authentication, and input validation.

30. **What is CORS and why is it important?**  
    Allows cross-origin requests between frontend (React) and backend (Node/Express).

---

## ⚛️ 31–40: React.js

31. **How to create a React component?**  
    ```js
    const Hello = () => <h1>Hello</h1>;
    ```

32. **What is state in React?**  
    Local component data managed with `useState`.

33. **How to use `useEffect`?**  
    ```js
    useEffect(() => {
      // side-effect
    }, []);
    ```

34. **How to handle forms in React?**  
    Controlled components using `value` and `onChange`.

35. **What is props drilling?**  
    Passing props through multiple levels of components.

36. **How to use Context API?**  
    Create a context and wrap components in a provider.

37. **What is React Router used for?**  
    Client-side routing and navigation.

38. **How to fetch API data in React?**  
    Use `fetch` or `axios` inside `useEffect`.

39. **How to handle conditional rendering in React?**  
    Using ternary: `{isLoggedIn ? <Logout /> : <Login />}`

40. **What are keys in React lists?**  
    Unique identifiers to help React efficiently update lists.

---

## 🔗 41–50: Integration & Deployment

41. **How does React communicate with Node/Express?**  
    Using HTTP requests (e.g., `axios`, `fetch`) to backend API endpoints.

42. **How to connect MERN stack components?**  
    - React makes requests to Express  
    - Express handles routes  
    - MongoDB stores/fetches data

43. **How to deploy a MERN app?**  
    - Backend: Render, Railway, VPS  
    - Frontend: Netlify, Vercel  
    - Use environment variables & separate build

44. **How to build React for production?**  
    `npm run build` — creates static `build/` folder.

45. **How to store environment variables?**  
    Use `.env` file for secrets like DB URIs, API keys.

46. **How to secure a MERN app?**  
    - Use HTTPS  
    - Input validation  
    - Authentication (JWT)  
    - Helmet/CORS

47. **How to implement authentication in MERN?**  
    - Backend: JWT auth using `jsonwebtoken`  
    - Frontend: Store token in localStorage or cookie

48. **How to test MERN applications?**  
    - React: Jest + React Testing Library  
    - Node/Express: Supertest + Jest/Mocha

49. **How to handle global errors in MERN?**  
    Catch errors in backend and send proper response; show friendly messages in frontend.

50. **What are common challenges in MERN?**  
    - CORS issues  
    - Asynchronous bugs  
    - State management  
    - Authentication flow

````
