# Top 50 React.js Questions for MERN Stack Developers (WorkElate)

## 🧠 React Basics

1. **What is React?**  
   A JavaScript library for building user interfaces using components.

2. **What is JSX?**  
   JSX stands for JavaScript XML. It allows writing HTML inside JavaScript.

3. **What are components in React?**  
   Reusable building blocks for UI. Two types: Functional and Class components.

4. **What is the virtual DOM?**  
   A lightweight copy of the actual DOM used for efficient UI updates.

5. **Why is React popular?**  
   Component-based, fast, scalable, and maintained by Meta (Facebook).

---

## 🔁 Functional Components & Hooks

6. **How to create a functional component?**  
   ```js
   const Hello = () => <h1>Hello</h1>;
````

7. **What are React Hooks?**
   Special functions like `useState` and `useEffect` for managing state/lifecycle in functional components.

8. **How to use `useState`?**

   ```js
   const [count, setCount] = useState(0);
   ```

9. **How to use `useEffect`?**

   ```js
   useEffect(() => {
     console.log("Mounted");
   }, []);
   ```

10. **What is the dependency array in `useEffect`?**
    It defines when the effect should run. Empty array = only on mount.

---

## ⛓️ Props & State

11. **What are props?**
    Read-only inputs to components. Passed from parent to child.

12. **How to pass props?**

    ```js
    <Greeting name="Sandeep" />
    ```

13. **How to access props?**

    ```js
    const Greeting = ({ name }) => <p>Hello {name}</p>;
    ```

14. **What is state?**
    Data managed within the component, using `useState` or class component's state.

15. **Props vs State?**

    * Props: External & read-only
    * State: Internal & mutable

---

## 🌀 Conditional Rendering

16. **How to conditionally render in JSX?**

    ```js
    {isLoggedIn ? <Logout /> : <Login />}
    ```

17. **Using `&&` for rendering:**

    ```js
    {show && <p>Visible</p>}
    ```

18. **What is a fragment in React?**
    A wrapper that doesn’t create extra DOM: `<></>`

19. **What is optional chaining?**
    Safe way to access deeply nested props: `user?.name`

20. **Short-circuit rendering vs ternary?**

    * Short-circuit: Only renders if true
    * Ternary: Renders one of two options

---

## 📚 Forms & Events

21. **How to handle input change in React?**

    ```js
    const handleChange = (e) => setName(e.target.value);
    ```

22. **How to submit a form?**

    ```js
    const handleSubmit = (e) => {
      e.preventDefault();
      // logic here
    };
    ```

23. **Controlled vs uncontrolled components?**

    * Controlled: Value managed via state
    * Uncontrolled: Managed by DOM itself

24. **How to bind input with state?**

    ```js
    <input value={name} onChange={handleChange} />
    ```

25. **What is `e.preventDefault()`?**
    Prevents default form submit behavior (like page reload).

---

## 📦 Lists & Keys

26. **How to render a list in React?**

    ```js
    items.map((item) => <li key={item.id}>{item.name}</li>)
    ```

27. **Why are keys important in lists?**
    Helps React identify which items changed, added, or removed.

28. **What happens if no key is given?**
    React may re-render unnecessarily and break component state.

29. **Why avoid index as key?**
    Causes problems if the list changes due to position mismatch.

30. **Can you use objects in lists?**
    Yes, but map them to JSX with a unique key.

---

## 🔄 Lifecycle & Performance

31. **What are lifecycle methods?**
    Functions triggered at different points of a component’s life (only in class components).

32. **React lifecycle phases?**

    * Mounting
    * Updating
    * Unmounting

33. **How to mimic lifecycle in hooks?**
    `useEffect` handles all lifecycle needs.

34. **What is cleanup in `useEffect`?**
    Code run when component unmounts:

    ```js
    return () => console.log("Cleanup");
    ```

35. **What is memoization?**
    Optimizing performance by caching values/functions using `useMemo` or `React.memo`.

---

## 🧱 Advanced Features

36. **What is Context API?**
    Way to share state globally across components without props drilling.

37. **How to create context?**

    ```js
    const MyContext = React.createContext();
    ```

38. **What is `useContext`?**
    A hook to access the nearest context value.

39. **What is `useRef` used for?**

    * Reference DOM elements
    * Store mutable values that don’t cause re-render

40. **What is `useReducer`?**
    Alternative to `useState` for complex state logic.

---

## 🧩 Routing & Integration

41. **Which library is used for routing in React?**
    `react-router-dom`

42. **How to define routes?**

    ```js
    <Route path="/about" element={<About />} />
    ```

43. **How to navigate programmatically?**

    ```js
    const navigate = useNavigate();
    navigate('/home');
    ```

44. **How to create a link in React?**

    ```js
    <Link to="/about">About</Link>
    ```

45. **How to fetch API data in React?**

    ```js
    useEffect(() => {
      fetch("/api").then(res => res.json()).then(setData);
    }, []);
    ```

---

## 🧪 Testing & Deployment

46. **How to deploy a React app?**

    * Build: `npm run build`
    * Upload `build/` to Netlify, Vercel, or static host

47. **How to create a production build?**
    `npm run build`

48. **Popular tools for testing React?**

    * Jest
    * React Testing Library
    * Cypress

49. **How to test a component render?**

    ```js
    render(<MyComponent />);
    expect(screen.getByText('Hello')).toBeInTheDocument();
    ```

50. **How to mock API calls in tests?**
    Use `jest.mock()` or libraries like `msw` (Mock Service Worker)

```
