# React Native Interview Questions

## 1. What is React Native?

**Answer:**
React Native is an open-source framework developed by Facebook that allows developers to build mobile applications using JavaScript and React. It enables the development of cross-platform apps for iOS and Android with a single codebase. Unlike traditional hybrid apps, React Native uses native components, providing a more native-like performance and user experience.

## 2. What are the main differences between React Native and React?

**Answer:**

- **Platform Target:** React is used for web development, while React Native is used for mobile app development.
- **Rendering:** React renders HTML elements on the web, whereas React Native uses native components (like `View`, `Text`, and `Image`) for mobile UIs.
- **Styling:** React uses CSS for styling, while React Native uses a subset of CSS-like properties, implemented using JavaScript objects.
- **Navigation:** React Native has specific navigation libraries (e.g., `react-navigation`), whereas React web apps use libraries like `react-router`.

## 3. How does React Native handle styling?

**Answer:**
React Native uses a style system similar to CSS but implemented using JavaScript objects. Styles are applied using the `style` prop on components. Unlike traditional CSS, React Native does not support all CSS properties but provides a subset tailored for mobile development. Styles are defined using properties like `flex`, `margin`, `padding`, `border`, and others.

```jsx
<View style={{ padding: 10, backgroundColor: "blue" }}>
  <Text style={{ color: "white" }}>Hello, World!</Text>
</View>
```

## 4. What is a "native module" in React Native?

**Answer:**
A native module in React Native allows you to call native code (written in Java/Objective-C/Swift) from JavaScript. This is useful for accessing platform-specific features that are not directly available in React Native. Native modules can be written in Java or Kotlin for Android and Objective-C or Swift for iOS.

To create a native module, you need to:

1. Write the native code.
2. Create a bridge to expose the native functionality to JavaScript.
3. Use the native module in your JavaScript code.

## 5. What is the purpose of the `useEffect` hook in React Native?

**Answer:**
The `useEffect` hook in React Native is used to perform side effects in functional components. It can be used for tasks such as data fetching, subscriptions, or manually changing the DOM. The hook takes two arguments: a function to run after the render, and an optional dependency array that determines when the effect should run.

```jsx
useEffect(() => {
  // Side effect code here
  return () => {
    // Cleanup code here
  };
}, [dependencies]);
```

## 6. How does React Native handle performance optimization?

**Answer:**
React Native provides several techniques for performance optimization, including:

- **PureComponent and memo:** These components help avoid unnecessary re-renders by shallowly comparing props and state.
- **FlatList and SectionList:** For rendering large lists of data, these components efficiently handle data by rendering only the visible items and using a virtualized list.
- **Optimization with `shouldComponentUpdate`:** This lifecycle method (or `React.memo` in functional components) helps in controlling when a component should re-render.
- **Use of native driver:** For animations, using the native driver (`useNativeDriver: true`) helps in offloading animation calculations to the native side for smoother animations.

## 7. What are some common libraries used with React Native?

**Answer:**
Some commonly used libraries with React Native include:

- **`react-navigation`** for navigation and routing.
- **`redux`** and **`@reduxjs/toolkit`** for state management.
- **`axios`** or **`fetch`** for making network requests.
- **`react-native-gesture-handler`** for handling gestures.
- **`react-native-reanimated`** for advanced animations.
- **`react-native-firebase`** for integrating Firebase services.

## 8. What is the significance of the `key` prop in React Native lists?

**Answer:**
The `key` prop in React Native lists is used to uniquely identify each item in a list. It helps React Native efficiently update and manage the list items by providing a stable identity for each element. This reduces the performance cost associated with re-rendering lists by ensuring that items are properly tracked and updated.

```jsx
<FlatList
  data={data}
  renderItem={({ item }) => <Text key={item.id}>{item.title}</Text>}
/>
```

## 9. Explain how to use the `useState` hook in React Native.

**Answer:**
The `useState` hook is used to add state to functional components in React Native. It returns an array with two elements: the current state value and a function to update that state.

```jsx
const [count, setCount] = useState(0);

const increment = () => {
  setCount(count + 1);
};

return (
  <View>
    <Text>Count: {count}</Text>
    <Button title="Increment" onPress={increment} />
  </View>
);
```

## 10. What are the steps to debug a React Native app?

**Answer:**
To debug a React Native app, you can use several approaches:

- **React Native Debugger:** A standalone app that integrates with Redux DevTools and Chrome DevTools.
- **Chrome Developer Tools:** By enabling remote debugging, you can use the Chrome DevTools for inspecting and debugging JavaScript code.
- **Flipper:** A platform for debugging iOS and Android apps, with support for React Native.
- **Console logs:** Use `console.log` to output information to the Metro bundler console or the debugging tools.
- **Error boundaries:** Implement error boundaries to catch JavaScript errors in component trees.

## 11. What is the role of `AppRegistry` in React Native?

**Answer:**
`AppRegistry` is the entry point for a React Native application. It is responsible for registering the root component of the app and starting the app’s lifecycle. The `AppRegistry.registerComponent` method takes two arguments: the name of the app and a function that returns the root component.

```jsx
import { AppRegistry } from "react-native";
import App from "./App";
import { name as appName } from "./app.json";

AppRegistry.registerComponent(appName, () => App);
```

## 12. What is the significance of the `Context API` in React Native?

**Answer:**
The Context API in React is used to manage and share state globally within a React application without passing props manually through every level of the component tree. It provides a way to share values like themes, user data, or app settings between components without having to explicitly pass props down through multiple layers.

```jsx
const MyContext = React.createContext();

const App = () => (
  <MyContext.Provider value="someValue">
    <MyComponent />
  </MyContext.Provider>
);

const MyComponent = () => {
  const value = React.useContext(MyContext);
  return <Text>{value}</Text>;
};
```

## 13. How do you handle deep linking in React Native?

**Answer:**
Deep linking allows users to open specific parts of your app from external links. To handle deep linking in React Native:

1. **Configure URL Schemes:** For iOS, configure URL schemes in the Info.plist file. For Android, add intent filters in the AndroidManifest.xml file.
2. **Use Linking API:** React Native provides the `Linking` module to handle deep links. You can use it to retrieve and process incoming URLs.

```jsx
import { Linking } from "react-native";

Linking.addEventListener("url", handleOpenURL);

const handleOpenURL = (event) => {
  console.log(event.url);
};

// To open a URL programmatically
Linking.openURL("myapp://path/to/screen");
```

## 14. What is the purpose of `React.memo`?

**Answer:**
`React.memo` is a higher-order component that optimizes performance by memoizing the result of a functional component. It prevents unnecessary re-renders of the component by only re-rendering when the props have changed. This can be particularly useful for components that render the same output given the same props.

```jsx
const MyComponent = React.memo(({ name }) => {
  console.log("Rendering:", name);
  return <Text>{name}</Text>;
});
```

## 15. How do you manage state in React Native applications?

**Answer:**
State management in React Native can be handled using:

- **Local State:** Using `useState` and `useReducer` hooks for managing component-specific state.
- **Context API:** For sharing state across multiple components without prop drilling.
- **State Management Libraries:** Libraries like `Redux`, `MobX`, or `Recoil` for more complex state management scenarios.
- **React Query or SWR:** For managing and caching server-side data.

## 16. What is `React Navigation` and how does it work?

**Answer:**
`React Navigation` is a library for managing navigation and routing in React Native applications. It provides a range of navigators such as stack navigators, tab navigators, and drawer navigators to handle different navigation patterns. The library relies on the concept of a navigation tree and enables navigating between screens using the `navigation` prop.

```jsx
import { createStackNavigator } from "@react-navigation/stack";
import { NavigationContainer } from "@react-navigation/native";

const Stack = createStackNavigator();

const App = () => (
  <NavigationContainer>
    <Stack.Navigator>
      <Stack.Screen name="Home" component={HomeScreen} />
      <Stack.Screen name="Details" component={DetailsScreen} />
    </Stack.Navigator>
  </NavigationContainer>
);
```

## 17. What is the difference between `Component` and `PureComponent` in React Native?

**Answer:**

- **`Component`:** The base class for creating a React component. It re-renders whenever its state or props change.
- **`PureComponent`:** A subclass of `Component` that performs a shallow comparison of props and state to determine if the component should re-render. This can improve performance by avoiding unnecessary re-renders.

```jsx
class MyComponent extends React.PureComponent {
  render() {
    return <Text>{this.props.name}</Text>;
  }
}
```

## 18. How do you handle offline data in React Native?

**Answer:**
To handle offline data in React Native, you can use:

- **Local Storage:** Libraries like `AsyncStorage` or `MMKVStorage` for storing key-value pairs.
- **SQLite:** For relational data storage with the `react-native-sqlite-storage` library.
- **PouchDB/CouchDB:** For more complex offline-first strategies and synchronization.

## 19. How do you optimize images in a React Native application?

**Answer:**
To optimize images in React Native:

- **Use the `Image` component properly:** Provide the `source` prop with appropriate image resolutions and sizes.
- **Use `ImageBackground` for better performance:** For static images used as backgrounds.
- **Leverage caching:** Use libraries like `react-native-fast-image` to handle image caching and performance.
- **Optimize image sizes:** Use tools to compress and resize images before including them in your app.

```jsx
import FastImage from "react-native-fast-image";

<FastImage
  style={{ width: 200, height: 200 }}
  source={{ uri: "https://example.com/image.jpg" }}
  resizeMode={FastImage.resizeMode.contain}
/>;
```

## 20. What is `Expo` and how does it relate to React Native?

**Answer:**
Expo is a framework and platform built around React Native that provides tools and services for developing, building, and deploying React Native applications. It includes a set of libraries and APIs that make it easier to work with React Native, especially for beginners. Expo also offers a managed workflow, allowing developers to use a set of pre-configured libraries without having to deal with native code directly.

- **Managed Workflow:** Simplifies development with pre-built configurations and tools.
- **Bare Workflow:** Provides more flexibility by allowing you to use custom native code.

## 21. What is the difference between `componentDidMount` and `useEffect`?

**Answer:**

- **`componentDidMount`:** A lifecycle method in class components that is called once, immediately after the component is added to the DOM. It's used for initialization tasks like data fetching.
- **`useEffect`:** A hook used in functional components that runs after the component renders. It can be used to perform side effects like data fetching, subscriptions, or manually changing the DOM. It can mimic the behavior of `componentDidMount` by providing an empty dependency array.

```jsx
// Using componentDidMount in a class component
class MyComponent extends React.Component {
  componentDidMount() {
    // Perform actions after component mounts
  }
}

// Using useEffect in a functional component
const MyComponent = () => {
  useEffect(() => {
    // Perform actions after component mounts
  }, []);
};
```

## 22. What are some common performance pitfalls in React Native?

**Answer:**

- **Re-renders:** Unnecessary re-renders can be caused by improper use of state and props. Use `React.memo`, `PureComponent`, or `shouldComponentUpdate` to optimize.
- **Large Lists:** Rendering large lists without optimization can impact performance. Use `FlatList` or `SectionList` with proper key props and memoization.
- **Expensive Operations:** Expensive operations or computations within render methods can slow down the app. Use memoization with `useMemo` or `useCallback`.
- **Unoptimized Images:** Large or unoptimized images can affect performance. Use `FastImage` or optimize images for different resolutions.

## 23. What is the role of `useCallback` and `useMemo` hooks?

**Answer:**

- **`useCallback`:** A hook that returns a memoized version of a callback function, which helps prevent unnecessary re-creations of functions between renders. It is useful when passing functions as props to child components.

```jsx
const handleClick = useCallback(() => {
  // Handle click
}, []);
```

- **`useMemo`:** A hook that returns a memoized value of a computation. It helps to optimize performance by preventing expensive calculations from running on every render.

```jsx
const computedValue = useMemo(() => {
  return expensiveComputation(input);
}, [input]);
```

## 24. How do you handle animations in React Native?

**Answer:**
React Native provides several options for handling animations:

- **`Animated` API:** A core module for creating smooth, interactive animations.
- **`react-native-reanimated`:** A library for more advanced animations with improved performance and capabilities.
- **`react-native-animatable`:** A library with pre-built animations and easier-to-use API.

```jsx
import { Animated } from "react-native";

const fadeAnim = useRef(new Animated.Value(0)).current;

useEffect(() => {
  Animated.timing(fadeAnim, {
    toValue: 1,
    duration: 1000,
    useNativeDriver: true,
  }).start();
}, []);

return <Animated.View style={{ opacity: fadeAnim }} />;
```

## 25. What is the purpose of `useReducer` hook and how is it different from `useState`?

**Answer:**

- **`useReducer`:** A hook used for managing more complex state logic in functional components. It is an alternative to `useState` for managing state transitions based on actions. It’s ideal for scenarios where state depends on previous state or involves multiple sub-values.

```jsx
const [state, dispatch] = useReducer(reducer, initialState);
```

- **`useState`:** A simpler hook for managing state where the state is usually independent or doesn't require complex updates.

```jsx
const [count, setCount] = useState(0);
```

## 26. What is the role of `getDerivedStateFromProps`?

**Answer:**
`getDerivedStateFromProps` is a static lifecycle method in class components that is called before rendering, both on the initial mount and on subsequent updates. It is used to update the state in response to prop changes. It replaces `componentWillReceiveProps` in newer React versions.

```jsx
static getDerivedStateFromProps(nextProps, prevState) {
  // Return an object to update state based on props
  return { derivedState: nextProps.someValue };
}
```

## 27. How do you handle error boundaries in React Native?

**Answer:**
Error boundaries are used to catch JavaScript errors in React component trees and display a fallback UI instead of crashing the entire app. Implementing error boundaries involves creating a class component with `componentDidCatch` and `static getDerivedStateFromError` methods.

```jsx
class ErrorBoundary extends React.Component {
  constructor(props) {
    super(props);
    this.state = { hasError: false };
  }

  static getDerivedStateFromError() {
    return { hasError: true };
  }

  componentDidCatch(error, info) {
    // Log error information
  }

  render() {
    if (this.state.hasError) {
      return <Text>Something went wrong.</Text>;
    }

    return this.props.children;
  }
}
```

## 28. What are the different types of navigators in React Navigation?

**Answer:**
React Navigation provides several types of navigators:

- **Stack Navigator:** Manages a stack of screens, allowing navigation through a stack-based approach (e.g., push and pop operations).
- **Tab Navigator:** Manages a tab-based navigation where each tab represents a different screen.
- **Drawer Navigator:** Manages navigation with a sliding drawer that reveals different sections of the app.
- **Material Top Tabs Navigator:** Similar to Tab Navigator but styled according to Material Design principles.

```jsx
import { createStackNavigator } from "@react-navigation/stack";
import { createBottomTabNavigator } from "@react-navigation/bottom-tabs";

const Stack = createStackNavigator();
const Tab = createBottomTabNavigator();
```

## 29. How do you use `react-native-gesture-handler`?

**Answer:**
`react-native-gesture-handler` is a library used to handle gestures in React Native applications. It provides a more flexible and performant way to handle touch events compared to the built-in gesture system.

To use `react-native-gesture-handler`, you need to:

1. Install the library.
2. Import and use gesture handler components like `PanGestureHandler`, `TapGestureHandler`, etc.

```bash
npm install react-native-gesture-handler
```

```jsx
import { PanGestureHandler } from "react-native-gesture-handler";

const MyComponent = () => {
  return (
    <PanGestureHandler onGestureEvent={handleGesture}>
      <View style={styles.box} />
    </PanGestureHandler>
  );
};
```

## 30. What is the purpose of `react-native-vector-icons`?

**Answer:**
`react-native-vector-icons` is a library that provides a large collection of customizable icons that can be used in React Native applications. It supports multiple icon sets like FontAwesome, MaterialIcons, and Ionicons, and allows for easy customization and integration of icons in your app.

```bash
npm install react-native-vector-icons
```

```jsx
import Icon from "react-native-vector-icons/FontAwesome";

const MyComponent = () => <Icon name="rocket" size={30} color="#900" />;
```

## 31. What is the difference between `useEffect` and `useLayoutEffect`?

**Answer:**

- **`useEffect`:** This hook runs after the DOM has been updated. It is useful for side effects that do not need to block the painting of the screen, such as data fetching, subscriptions, and manually modifying the DOM.

```jsx
useEffect(() => {
  // Side effect code here
}, [dependencies]);
```

- **`useLayoutEffect`:** This hook runs synchronously after all DOM mutations. It is useful for measuring the layout or making adjustments before the browser has a chance to paint.

```jsx
useLayoutEffect(() => {
  // Layout effect code here
}, [dependencies]);
```

## 32. What is the difference between `React Navigation` and `React Router`?

**Answer:**

- **React Navigation:** A navigation library specifically designed for React Native. It supports stack, tab, and drawer navigators, and is optimized for mobile navigation patterns.
- **React Router:** A routing library for React used primarily in web applications. It provides route management and rendering based on URL paths and is not optimized for mobile-specific navigation patterns.

## 33. How do you handle accessibility in React Native?

**Answer:**
React Native provides built-in support for accessibility features. You can handle accessibility by:

- **Using `accessible` prop:** Marks a component as accessible.
- **Using `accessibilityLabel`:** Provides a label for screen readers.
- **Using `accessibilityHint`:** Gives additional information about the purpose of the element.
- **Testing with Accessibility Inspector:** Tools like the Accessibility Inspector in Xcode or Android Studio can help test and improve accessibility.

```jsx
<Button
  title="Submit"
  onPress={handlePress}
  accessibilityLabel="Submit button"
  accessibilityHint="Press to submit the form"
/>
```

## 34. What are `refs` in React Native and how do you use them?

**Answer:**
Refs provide a way to access and interact with DOM nodes or React elements directly. They are useful for managing focus, triggering animations, or integrating with third-party libraries.

- **Creating a ref:** Use `React.createRef()` in class components or `useRef()` in functional components.
- **Assigning a ref:** Attach the ref to a React element via the `ref` attribute.

```jsx
// Functional component with useRef
const MyComponent = () => {
  const inputRef = useRef(null);

  const focusInput = () => {
    inputRef.current.focus();
  };

  return <TextInput ref={inputRef} placeholder="Type here" />;
};
```

## 35. How do you perform data fetching in React Native?

**Answer:**
Data fetching in React Native is similar to how it is done in React. Common methods include:

- **Using `fetch`:** A built-in API for making network requests.

```jsx
useEffect(() => {
  fetch("https://api.example.com/data")
    .then((response) => response.json())
    .then((data) => setData(data))
    .catch((error) => console.error(error));
}, []);
```

- **Using `axios`:** A popular HTTP client for making requests.

```jsx
import axios from "axios";

useEffect(() => {
  axios
    .get("https://api.example.com/data")
    .then((response) => setData(response.data))
    .catch((error) => console.error(error));
}, []);
```

## 36. What are `PropTypes` and how are they used in React Native?

**Answer:**
`PropTypes` is a library for type-checking props in React components. It helps to validate the types of props passed to components and can be useful for catching bugs related to incorrect prop types.

```jsx
import PropTypes from "prop-types";

const MyComponent = ({ name, age }) => (
  <Text>
    {name} is {age} years old
  </Text>
);

MyComponent.propTypes = {
  name: PropTypes.string.isRequired,
  age: PropTypes.number.isRequired,
};
```

## 37. What is the `StyleSheet` API in React Native?

**Answer:**
The `StyleSheet` API is used to create a style object in React Native. It helps to optimize styles by ensuring that style objects are created only once and are not recreated on every render.

```jsx
import { StyleSheet, View, Text } from "react-native";

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: "center",
    alignItems: "center",
  },
  text: {
    fontSize: 20,
  },
});

const MyComponent = () => (
  <View style={styles.container}>
    <Text style={styles.text}>Hello, World!</Text>
  </View>
);
```

## 38. How do you handle navigation state persistence in React Navigation?

**Answer:**
To persist navigation state in React Navigation:

- **Use AsyncStorage:** Save and retrieve navigation state from AsyncStorage.

```jsx
import AsyncStorage from "@react-native-async-storage/async-storage";

const persistNavigationState = async (state) => {
  try {
    await AsyncStorage.setItem("navigationState", JSON.stringify(state));
  } catch (error) {
    console.error(error);
  }
};

const getNavigationState = async () => {
  try {
    const state = await AsyncStorage.getItem("navigationState");
    return state ? JSON.parse(state) : undefined;
  } catch (error) {
    console.error(error);
  }
};
```

- **Integrate with React Navigation:** Use `onStateChange` and `initialState` props of the navigation container to handle persistence.

## 39. What are `NativeModules` and `NativeEventEmitter` in React Native?

**Answer:**

- **`NativeModules`:** A JavaScript object that provides access to native modules in React Native. It allows you to call native functions from JavaScript.

```jsx
import { NativeModules } from "react-native";

const { CustomNativeModule } = NativeModules;
CustomNativeModule.customFunction();
```

- **`NativeEventEmitter`:** A class that allows you to listen to events emitted from native modules. It helps in subscribing and unsubscribing from native events.

```jsx
import { NativeEventEmitter, NativeModules } from "react-native";

const { CustomNativeModule } = NativeModules;
const eventEmitter = new NativeEventEmitter(CustomNativeModule);

const subscription = eventEmitter.addListener("EventName", (event) => {
  console.log(event);
});

return () => subscription.remove();
```

## 40. How do you integrate Firebase with a React Native application?

**Answer:**
To integrate Firebase with a React Native application:

1. **Install Firebase SDK:** Use `@react-native-firebase/app` and specific packages for the Firebase services you need.

```bash
npm install @react-native-firebase/app @react-native-firebase/auth @react-native-firebase/firestore
```

2. **Configure Firebase:** Follow the setup instructions in the Firebase console to configure your app for iOS and Android.

3. **Use Firebase Services:** Import and use Firebase services in your React Native components.

```jsx
import auth from "@react-native-firebase/auth";

const signIn = async () => {
  try {
    await auth().signInWithEmailAndPassword("email@example.com", "password");
  } catch (error) {
    console.error(error);
  }
};
```
