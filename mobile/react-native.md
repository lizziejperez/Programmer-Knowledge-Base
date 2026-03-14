# React Native

React Native is a cross-platform framework for building mobile applications using JavaScript and React.

It allows developers to write mobile apps for:

- iOS
- Android

Using:

- JavaScript / TypeScript
- React components
- Native UI primitives (not HTML)

## Installation

React Native apps are commonly created using:

### Expo (recommended for beginners)

```bash
npx create-expo-app myApp
```

What this does:

- Downloads the Expo project template
- Creates a folder called myApp
- Installs React Native and dependencies
- Sets up a working mobile project

Result:

```
myApp/
├── App.js
├── package.json
├── node_modules/
```

Then you run the app with:

```bash
cd myApp
npm start
```

### React Native CLI

```bash
npx react-native init myApp
```

This creates a React Native project **without Expo**.

It includes the full native project structure:

```
myApp/
├── android/
├── ios/
├── App.js
├── package.json
```

You use this when you need direct access to native code.

## 1. Core Idea

React Native uses:

- React's component model
- Native platform components
- A JavaScript bridge to communicate with native code

Unlike React (web), it does **not** render HTML.

Instead of:

```jsx
<div>
  <p>Hello</p>
</div>
```

You use:

```javascript
<View>
  <Text>Hello</Text>
</View>
```

## 2. Basic App Structure

Example:

```javascript
import React from 'react';
import { View, Text } from 'react-native';

export default function App() {
  return (
    <View>
      <Text>Hello World</Text>
    </View>
  );
}
```

### Core Components

| Component    | Purpose                  |
| ------------ | ------------------------ |
| `View`       | Container (like div)     |
| `Text`       | Text display             |
| `Image`      | Display images           |
| `ScrollView` | Scrollable container     |
| `FlatList`   | Efficient list rendering |
| `TextInput`  | User input               |
| `Button`     | Basic button             |

## 3. Styling

React Native uses JavaScript objects for styling (not CSS files).

```javascript
import { StyleSheet } from 'react-native';

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
  },
});
```

Applied like:

```javascript
<View style={styles.container}>
```

### Layout System

React Native uses Flexbox by default.

Key properties:

```javascript
flex: 1
flexDirection: 'row' | 'column'
justifyContent: 'center'
alignItems: 'center'
```

Default differences from web:

- `flexDirection` defaults to column
- No CSS Grid
- No floats

## 4. State & Hooks

React Native uses the same React hooks:

```javascript
import { useState } from 'react';

const [count, setCount] = useState(0);
```

Common hooks:

- `useState`
- `useEffect`
- `useContext`
- `useRef`

## 5. Navigation

React Native does not include built-in routing.

Common solution:

- React Navigation

Example concepts:

- Stack navigation
- Tab navigation
- Drawer navigation

Navigation is component-based rather than URL-based.

## 6. Lists

Use `FlatList` for performance:

```javascript
<FlatList
  data={data}
  renderItem={({ item }) => <Text>{item.title}</Text>}
  keyExtractor={(item) => item.id}
/>
```

`FlatList` improves performance by rendering only visible items.

## 7. Handling User Input

```javascript
<TextInput
  value={text}
  onChangeText={setText}
/>
```

Unlike web React:

- There is no DOM
- Events are handled through component props
- Input handlers are provided directly by components

## 8. Platform Differences

React Native allows platform-specific behavior.

```javascript
import { Platform } from 'react-native';

if (Platform.OS === 'ios') {
  // iOS-specific code
}
```

You can also create:

```
Component.ios.js
Component.android.js
```

## 9. Native Modules

React Native can communicate with native platform APIs.

Used for:

- Camera access
- File system
- Push notifications
- Bluetooth
- Sensors

Libraries often wrap native modules.

## 10. Performance Considerations

React Native runs JavaScript in a separate thread.

Performance depends on:

- Avoiding excessive re-renders
- Proper list virtualization
- Memoization
- Efficient state updates

Tools:

- `React.memo`
- `useCallback`
- `useMemo`

## 11. Expo vs React Native CLI

### Expo

- Managed workflow
- Faster setup
- Preconfigured tools
- Limited direct native modification (without ejecting)

### React Native CLI

- Full native control
- More configuration
- Required for custom native modules

## 12. File Structure Example

```
src/
├── components/
├── screens/
├── navigation/
├── hooks/
├── context/
├── services/
└── App.js
```

Separation:

- Components → Reusable UI
- Screens → Full pages
- Navigation → Routing logic
- Services → API calls
- Hooks → Custom logic

## 13. Theming

Use centralized color variables:

```javascript
export const theme = {
  colors: {
    primary: '#32363c',
    background: '#f8f9fa',
    text: '#212529',
  },
};
```

Apply:

```javascript
<View style={{ backgroundColor: theme.colors.background }}>
```

Or use Context for dynamic theme switching.

## 14. Comparison: React vs React Native

| Feature   | React (Web)    | React Native         |
| --------- | -------------- | -------------------- |
| Rendering | DOM            | Native components    |
| Styling   | CSS            | JS StyleSheet        |
| Routing   | URL-based      | Navigation-based     |
| Layout    | Flexbox + Grid | Flexbox only         |
| Platform  | Browser        | Mobile (iOS/Android) |

## 15. When to Use React Native

Use React Native when:

- You want one codebase for iOS and Android
- You are comfortable with React
- You don’t need heavy native graphics engines
- Development speed matters

Avoid React Native when:

- You need advanced 3D rendering
- You need deep OS-level integration
- You require maximum performance (consider native or Flutter)

## Summary

React Native combines:

- React’s component architecture
- JavaScript logic
- Native UI rendering

It enables cross-platform mobile development with shared business logic and structured component design.