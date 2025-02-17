## React Native - Navigating Between Screens

Mobile apps use a navigation 'stack' to navigate between pages. The concept is similar to the browser:

- To navigate to a new screen, a page is 'pushed' onto the stack, adding to the navigation history.
- You can go back to the previous page by 'popping' a page off the stack.

Each platform has established patterns to achieve this.

<!-- break -->

### iOS

A new screen is pushed onto the stack, with the screen revealing from the right hand side of the screen.

A _Back_ button appears in the left hand side of the headerbar, to go back. You can also swipe from the left hand side of the display to achieve this.

### Android

A new screen is pushed, with the screen appearing with a gentle fade-in animation from the bottom of the screen.

A _Back_ button appears in the left hand side of the headerbar, to go back. You can also press the hardware back button to achieve this.

<!-- break -->

## React Navigation

The [React Navigation](https://reactnavigation.org) library applies these navigation patterns for use in a React Native app.

It is a third party dependency, install it with `npm`:

``` bash
npm install react-navigation
```

Using this library, set up a `StackNavigator`, which defines the different screens to navigate between. Each screen will be created as a separate React component.

Each screen will be rendered with a headerbar, and will also receive a `navigation` prop, which can be used to navigate to different pages.

<!-- break -->

### React Navigation Example

#### `screens/HomeScreen.js`

``` jsx
import React, { Component } from 'react';
import { Text } from 'react-native';

class HomeScreen extends Component {
  render() {
    return <Text>This is the Home Screen!</Text>;
  }
}

export default HomeScreen;
```

<!-- break -->

### React Navigation Example

#### `screens/InfoScreen.js`

``` jsx
import React, { Component } from 'react';
import { Text } from 'react-native';

class InfoScreen extends Component {
  render() {
    return <Text>This is the Info Screen!</Text>;
  }
}

export default InfoScreen;
```

<!-- break -->

### React Navigation Example

#### `App.js`

``` jsx
import {
  createStackNavigator,
  createAppContainer
} from 'react-navigation';

import HomeScreen from './screens/HomeScreen';
import InfoScreen from './screens/InfoScreen';

const RootNavigator = createStackNavigator({
  Home: HomeScreen,
  Info: InfoScreen
});

export default createAppContainer(RootNavigator);
```

<!-- break -->

## Controlling the headerbar

The headerbar can be controlled via a `navigationOptions` static property on the component.

Use this to set the headerbar title, style and buttons.

``` jsx
class HomeScreen extends Component {
  static navigationOptions = {
    title: 'Home',
    headerStyle: {
      backgroundColor: '#68aa63'
    },
    headerTintColor: '#ffffff'
  }
}
```
<!-- break -->

### Stateless function component

If your `HomeScreen` component was a stateless function component, the above can be rewritten as:

``` jsx
const HomeScreen = () => ( /* ... */ );

HomeScreen.navigationOptions = {
    title: 'Home',
    headerStyle: {
      backgroundColor: '#68aa63'
    },
    headerTintColor: '#ffffff'
  }
};
```

<!-- break -->

### Status Bar

The status bar sits at the top of a mobile device. It includes information such as the current time, battery charge level and signal strength.

The colour of the status bar can be controlled using the `StatusBar` module:

``` js
import { StatusBar } from 'react-native';

// Change the text colour to white (iOS only)
StatusBar.setBarStyle('light-content');
```

<!-- break -->

## Navigating Between Screens

Each screen configured inside a `StackNavigator` will be passed a `navigation` prop. Use this to `navigate` to a new screen:

``` jsx
import { Button } from 'react-native';

class HomeScreen extends Component {
  constructor(props) {
    super(props);
    this.onPress = this.onPress.bind(this);
  }
  onPress() {
    this.props.navigation.navigate('Info');
  }
  render() {
    return <Button title="Info Screen" onPress={this.onPress} />;
  }
}
```

<!-- break -->

## Passing data to screen

Pass an object as the second argument to `navigate` to send data to the screen. Pull it out with `getParam()`:

``` jsx
class HomeScreen extends Component {
  onPress() {
    this.props.navigation.navigate('Info', {
      body: 'This is the Info Screen'
    });
  }
}

class InfoScreen extends Component {
  render() {
    const body = this.props.navigation.getParam('body');
    return <Text>{body}</Text>;
  }
}
```

<!-- break -->

## Passing headerbar data to screen

You can use the function form of `navigationOptions` to access the `navigation` object for use by the headerbar:

``` jsx
class HomeScreen extends Component {
  onPress() {
    this.props.navigation.navigate('InfoScreen', {
      title: 'Info'
    });
  }
}

class InfoScreen extends Component {
  static navigationOptions = ({navigation}) => ({
    title: navigation.getParam('title')
  });
}
```

<!-- break -->

## Updating headerbar globally

You can modify all instances of the headerbar in a `StackNavigator` by setting a `defaultNavigationOptions` property via a second argument:

``` js
const RootNavigator = createStackNavigator({
  Home: HomeScreen,
  Info: InfoScreen
}, {
  defaultNavigationOptions: {
    headerStyle: {
      backgroundColor: '#68aa63'
    },
    headerTintColor: '#ffffff'
  }
});
```

<!-- break -->

## Further Reading

- [React Navigation Docs](https://reactnavigation.org/docs/getting-started.html)
- [StatusBar](https://facebook.github.io/react-native/docs/statusbar.html)