# React Native project from stratch
Install all the dependencies as described in the react-native [docs](https://facebook.github.io/react-native/docs/getting-started)

*Run this to install a package or upgrade it to the latest version*
```sh
$ sudo npm install -g <package>
```
## Create a new React Native project 
```sh
$ expo init <project_name> && cd <project_name>
$ yarn eject
$ yarn add react-native
$ yarn upgrade-interactive --latest
```

## Fix ejected project
Remove `.expo` folder in the root of the project.
Create `index.js` file in the root of the project with the next lines:
```js
/** @format */

import { AppRegistry } from 'react-native';
import App from './App';
import { name as appName } from './app.json';

AppRegistry.registerComponent(appName, () => App);
```

Open `android/build.gradle` file and update next variables:
  * **buildToolsVersion** = https://developer.android.com/studio/releases/build-tools
  * **minSdkVersion** = don’t change
  * **compileSdkVersion** = Android Studio -> Tools -> SDK Manager -> The latest API Level
  * **targetSdkVersion** = compileSdkVersion - 1
  * **supportLibVersion** = https://developer.android.com/topic/libraries/support-library/revisions

Open the project’s `android` folder in Android Studio and wait until gradlew sync and build (Ignore Android Gradle Plugin Update).
Open  `Android Studio -> Tools -> AVD Manager` and launch any AVD in the emulator`

Type next commands:
```sh
$ cd <project_name>
$ yarn start
```
And in a new terminal (don't close previous):
```sh
$ yarn android
```

##### P.S.
*Press `rr` in the emulator to reload the app after changes you made in the code.*