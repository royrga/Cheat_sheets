---
tags:
  - Framework
---

# Expo 

Expo is an open-source framework and platform for building React Native applications. It provides a set of tools and services to streamline the development process, including:

- **Pre-configured Environment**: Simplifies setup with pre-built configurations.
- **Expo Go App**: Allows live preview and testing on physical devices.
- **Rich APIs**: Offers access to device features like camera, location, and notifications without native code.
- **Over-the-Air Updates**: Enables instant app updates without resubmission to app stores.
- **Cross-Platform Support**: Ensures compatibility across iOS, Android, and web.

Expo is ideal for developers seeking a fast and efficient way to build and deploy React Native apps.
## Table of Contents

- [Expo Router](#expo-router)
    - [Key Concepts](#key-concepts)
    - [Stack Navigation with Expo Router](#stack-navigation-with-expo-router)
    - [Setting Up Stack Navigation](#setting-up-stack-navigation)
    - [Key Features of Stack Navigation](#key-features-of-stack-navigation)


## Expo Router

Expo Router is a file-based routing solution for React Native applications, inspired by web frameworks like Next.js. It simplifies navigation by using the file system to define routes. When working with TypeScript, there are key concepts to consider:

### Key Concepts

1. **File-Based Routing**:
    - Routes are defined by the file structure in the `pages` directory.
    - For example, a file named `pages/home.tsx` corresponds to the `/home` route.

2. **Dynamic Routes**:
    - Use square brackets for dynamic segments, e.g., `pages/[id].tsx` for `/123`.
    - TypeScript types can be used to define the shape of route parameters.

3. **Type-Safe Navigation**:
    - Leverage TypeScript to ensure type safety when navigating between screens.
    - Use `useRouter` or `Link` components with typed route parameters.

4. **Layouts**:
    - Create reusable layouts by defining `_layout.tsx` files in directories.
    - Layouts wrap child routes and provide consistent UI structure.

5. **API Integration**:
    - Combine Expo Router with TypeScript to strongly type API responses and props passed between screens.

6. **Error Handling**:
    - Use `_error.tsx` to define a global error page for unhandled routes or exceptions.

By combining Expo Router with TypeScript, you can build scalable, type-safe navigation systems for your React Native applications.

### Stack Navigation with Expo Router

Expo Router supports stack navigation, allowing you to manage a stack of screens with a familiar push-and-pop behavior. This is particularly useful for workflows where users navigate deeper into a hierarchy of screens.

### Setting Up Stack Navigation

1. **Install Dependencies**:
    Ensure you have `expo-router` and `react-native-screens` installed in your project.

    ```bash
    npm install expo-router react-native-screens
    ```

2. **Define Stack Screens**:
    Create a `_layout.tsx` file in your `pages` directory to define the stack navigator.

    ```tsx
    // pages/_layout.tsx
    import { Stack } from 'expo-router';

    export default function Layout() {
      return (
         <Stack
            screenOptions={{
              headerStyle: { backgroundColor: '#f8f9fa' },
              headerTintColor: '#333',
            }}
         />
      );
    }
    ```

3. **Add Screens**:
    Add individual screens as files in the `pages` directory. For example:

    ```tsx
    // pages/home.tsx
    import { View, Text, Button } from 'react-native';
    import { useRouter } from 'expo-router';

    export default function HomeScreen() {
      const router = useRouter();

      return (
         <View>
            <Text>Home Screen</Text>
            <Button title="Go to Details" onPress={() => router.push('/details')} />
         </View>
      );
    }
    ```

    ```tsx
    // pages/details.tsx
    import { View, Text, Button } from 'react-native';
    import { useRouter } from 'expo-router';

    export default function DetailsScreen() {
      const router = useRouter();

      return (
         <View>
            <Text>Details Screen</Text>
            <Button title="Go Back" onPress={() => router.pop()} />
         </View>
      );
    }
    ```

#### Key Features of Stack Navigation

- **Header Customization**:
  Customize headers for individual screens using `screenOptions` or by defining options in the screen file.

  ```tsx
  // pages/details.tsx
  export const options = {
     title: 'Details Page',
     headerStyle: { backgroundColor: '#6200ee' },
     headerTintColor: '#fff',
  };
  ```

- **Nested Navigation**:
  Combine stack navigation with other navigators (e.g., tabs) by nesting layouts.

- **Deep Linking**:
  Automatically handles deep linking, allowing users to navigate directly to specific screens via URLs.

Stack navigation in Expo Router provides a powerful and flexible way to manage screen transitions in your React Native app, while maintaining a clean and type-safe codebase.

