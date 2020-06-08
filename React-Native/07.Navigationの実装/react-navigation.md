# React Navigation

 - [React-Navigatorを利用してみる（基礎編） - Qiita](https://qiita.com/zaburo/items/5b69a65db1b4d181896a)

React Navigationでは3つのナビゲーション機能を提供しています。

 - Stack Navigation
 - Tab Navigation
 - Drawer Navigation

このそれぞれの実装方法を見てみます。

## Stack Navigation

 - [createStackNavigator | React Navigation](https://reactnavigation.org/docs/stack-navigator/)

### インストール方法
```bash
npm install @react-navigation/stack
```

### 定義
```js
import { createStackNavigator } from '@react-navigation/stack';

const Stack = createStackNavigator();

function MyStack() {
  return (
    <Stack.Navigator>
      <Stack.Screen name="Home" component={Home} />
      <Stack.Screen name="Notifications" component={Notifications} />
      <Stack.Screen name="Profile" component={Profile} />
      <Stack.Screen name="Settings" component={Settings} />
    </Stack.Navigator>
  );
}
```


## Tab Navigation

 - [createBottomTabNavigator | React Navigation](https://reactnavigation.org/docs/bottom-tab-navigator/)



## Drawer Navigation

 - [Drawer navigation | React Navigation](https://reactnavigation.org/docs/drawer-based-navigation/)

```bash
npm install @react-navigation/drawer
```

`App.js`
```js
import * as React from 'react';
import { Button, View } from 'react-native';
import { createDrawerNavigator } from '@react-navigation/drawer';
import { NavigationContainer } from '@react-navigation/native';

function HomeScreen({ navigation }) {
  return (
    <View style={{ flex: 1, alignItems: 'center', justifyContent: 'center' }}>
      <Button
        onPress={() => navigation.navigate('Notifications')}
        title="Go to notifications"
      />
    </View>
  );
}

function NotificationsScreen({ navigation }) {
  return (
    <View style={{ flex: 1, alignItems: 'center', justifyContent: 'center' }}>
      <Button onPress={() => navigation.goBack()} title="Go back home" />
    </View>
  );
}

const Drawer = createDrawerNavigator();

export default function App() {
  return (
    <NavigationContainer>
      <Drawer.Navigator initialRouteName="Home">
        <Drawer.Screen name="Home" component={HomeScreen} />
        <Drawer.Screen name="Notifications" component={NotificationsScreen} />
      </Drawer.Navigator>
    </NavigationContainer>
  );
}
```