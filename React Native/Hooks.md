## Hooks

React Native supports React Hooks, which allow you to use state and other React features in functional components. Here are some commonly used hooks:

### Table of Contents

1. [useState](#usestate)
2. [useEffect](#useeffect)
3. [useContext](#usecontext)
4. [useReducer](#usereducer)
5. [useRef](#useref)
6. [useMemo](#usememo)
7. [useCallback](#usecallback)

### useState
Allows you to add state to functional components.
```javascript
const [count, setCount] = useState(0);
```

### useEffect
Used for side effects like data fetching, subscriptions, or manually changing the DOM.
```javascript
useEffect(() => {
    console.log('Component mounted');
    return () => console.log('Component unmounted');
}, []);
```

### useContext
Provides access to context values without using `Context.Consumer`.
```javascript
const theme = useContext(ThemeContext);
```

### useReducer
An alternative to `useState` for managing complex state logic.
```javascript
const [state, dispatch] = useReducer(reducer, initialState);
```

### useRef
Allows you to persist values across renders without causing re-renders.
```javascript
const inputRef = useRef(null);
```

### useMemo
Optimizes performance by memoizing expensive calculations.
```javascript
const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);
```

### useCallback
Memoizes callback functions to prevent unnecessary re-renders.
```javascript
const handleClick = useCallback(() => {
    console.log('Button clicked');
}, []);
```
