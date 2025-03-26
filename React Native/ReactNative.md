# React Native

Hooks simplify state management and lifecycle methods, making functional components more powerful and easier to maintain.
1. [Introduction](#introduction)
2. [Key Features](#key-features)
3. [Best Practices](#best-practices)
4. [Key Concepts](#key-concepts)
5. [Hooks](#hooks)
6. [Common components](#common-components)
7. [Useful Commands](#useful-commands)

Further references:  
- [Styles](Styles.md) 

## Introduction
React Native is an open-source framework developed by Facebook for building cross-platform mobile applications using JavaScript and React. It allows developers to create apps for iOS and Android with a single codebase, leveraging native components for better performance and a native-like user experience.

## Key Features
- **Cross-platform development**: Write once, run on both iOS and Android.
- **Native performance**: Uses native components for rendering.
- **Hot Reloading**: Enables fast iteration during development.
- **Large ecosystem**: Extensive library support and community contributions.

React Native is widely used for creating scalable and high-performance mobile applications.

## Best Practices
- **Component Reusability**: Break your UI into small, reusable components to improve maintainability.
- **State Management**: Use libraries like Redux, MobX, or React Context API for managing complex state.
- **Styling**: Use `StyleSheet` for consistent and optimized styling. Consider libraries like Styled Components for dynamic styling.
- **Performance Optimization**: Use `FlatList` or `SectionList` for rendering large datasets efficiently. Avoid unnecessary re-renders by using `React.memo` and `useCallback`.
- **Error Handling**: Implement proper error boundaries and use tools like Sentry for error tracking.
- **Testing**: Write unit tests with Jest and integration tests with tools like Detox.

## Key Concepts
- **JSX**: A syntax extension for JavaScript used to describe UI components.
- **Components**: The building blocks of a React Native app. Can be functional or class-based.
- **Props**: Short for "properties," used to pass data from parent to child components.
- **State**: A component's internal data that determines its behavior and rendering.
- **Lifecycle Methods**: Methods like `componentDidMount` and `useEffect` for managing side effects.
- **Navigation**: Use libraries like React Navigation for handling app navigation.
- **Native Modules**: Extend functionality by integrating native code for platform-specific features.
- **Expo**: A framework and platform for building React Native apps with pre-configured tools.

## Hooks

React Native supports React Hooks, which allow you to use state and other React features in functional components. Here are some commonly used hooks:

- **useState**: Allows you to add state to functional components.
    ```javascript
    const [count, setCount] = useState(0);
    ```

- **useEffect**: Used for side effects like data fetching, subscriptions, or manually changing the DOM.
    ```javascript
    useEffect(() => {
        console.log('Component mounted');
        return () => console.log('Component unmounted');
    }, []);
    ```

- **useContext**: Provides access to context values without using `Context.Consumer`.
    ```javascript
    const theme = useContext(ThemeContext);
    ```

- **useReducer**: An alternative to `useState` for managing complex state logic.
    ```javascript
    const [state, dispatch] = useReducer(reducer, initialState);
    ```

- **useRef**: Allows you to persist values across renders without causing re-renders.
    ```javascript
    const inputRef = useRef(null);
    ```

- **useMemo**: Optimizes performance by memoizing expensive calculations.
    ```javascript
    const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);
    ```

- **useCallback**: Memoizes callback functions to prevent unnecessary re-renders.
    ```javascript
    const handleClick = useCallback(() => {
        console.log('Button clicked');
    }, []);
    ```

    ## Common Components

    React Native provides a set of core components that are essential for building mobile applications. Here are some commonly used components:

    - **View**: A container component for laying out child components with support for styling and flexbox.
        ```javascript
        import { View } from 'react-native';

        const App = () => (
            <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
                {/* Child components go here */}
            </View>
        );
        ```

    - **Text**: Used for displaying text.
        ```javascript
        import { Text } from 'react-native';

        const App = () => (
            <Text style={{ fontSize: 18, color: 'blue' }}>
                Hello, React Native!
            </Text>
        );
        ```

    - **Button**: A basic button component for handling user interactions.
        ```javascript
        import { Button } from 'react-native';

        const App = () => (
            <Button title="Press Me" onPress={() => alert('Button Pressed!')} />
        );
        ```

    - **TextInput**: A component for user input.
        ```javascript
        import { TextInput } from 'react-native';

        const App = () => {
            const [text, setText] = useState('');
            return (
                <TextInput
                    style={{ height: 40, borderColor: 'gray', borderWidth: 1 }}
                    onChangeText={setText}
                    value={text}
                    placeholder="Type here"
                />
            );
        };
        ```

    - **Image**: Displays images from local or remote sources.
        ```javascript
        import { Image } from 'react-native';

        const App = () => (
            <Image
                source={{ uri: 'https://example.com/image.png' }}
                style={{ width: 100, height: 100 }}
            />
        );
        ```

    - **ScrollView**: A scrollable container for displaying content that overflows the screen.
        ```javascript
        import { ScrollView, Text } from 'react-native';

        const App = () => (
            <ScrollView>
                <Text>Item 1</Text>
                <Text>Item 2</Text>
                <Text>Item 3</Text>
            </ScrollView>
        );
        ```

    - **FlatList**: Optimized for rendering large lists of data.
        ```javascript
        import { FlatList, Text } from 'react-native';

        const App = () => {
            const data = [{ key: 'Item 1' }, { key: 'Item 2' }, { key: 'Item 3' }];
            return (
                <FlatList
                    data={data}
                    renderItem={({ item }) => <Text>{item.key}</Text>}
                    keyExtractor={(item, index) => index.toString()}
                />
            );
        };
        ```

    - **TouchableOpacity**: A wrapper for making views respond to touch with opacity feedback.
        ```javascript
        import { TouchableOpacity, Text } from 'react-native';

        const App = () => (
            <TouchableOpacity onPress={() => alert('Touchable Pressed!')}>
                <Text>Press Me</Text>
            </TouchableOpacity>
        );
        ```

    - **SafeAreaView**: Ensures content is rendered within the safe area boundaries of a device.
        ```javascript
        import { SafeAreaView, Text } from 'react-native';

        const App = () => (
            <SafeAreaView>
                <Text>Safe Area Content</Text>
            </SafeAreaView>
        );
        ```

    These components form the foundation of React Native applications and can be combined to create complex UIs.

## Useful Commands
- **Start Development Server**: `npx react-native start`
- **Run on iOS**: `npx react-native run-ios`
- **Run on Android**: `npx react-native run-android`
- **Install Dependencies**: `npm install` or `yarn install`
- **Build APK**: `npx react-native run-android --variant=release`
- **Clean Cache**: `watchman watch-del-all && rm -rf node_modules && npm install && npm start --reset-cache`