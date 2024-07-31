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
