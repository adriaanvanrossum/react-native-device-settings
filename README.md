# react-native-device-settings

React Native simple platform agnostic API to open up device settings menus

### This is a fork of [rjblopes](https://github.com/rjblopes/react-native-device-settings) package and fixes this error

```
:react-native-device-settings:compileReleaseJavaWithJavac
:react-native-device-settings:compileReleaseJavaWithJavac - is not incremental (e.g. outputs have changed, no previous execution, etc.).
/node_modules/react-native-device-settings/android/src/main/java/com/rjblopes/opensettings/OpenSettingsPackage.java:15: error: method does not override or implement a method from a supertype
    @Override
    ^
1 error
:react-native-device-settings:compileReleaseJavaWithJavac FAILED

FAILURE: Build failed with an exception.

* What went wrong:
Execution failed for task ':react-native-device-settings:compileReleaseJavaWithJavac'.
> Compilation failed; see the compiler error output for details.

* Try:
Run with --stacktrace option to get the stack trace. Run with --info or --debug option to get more log output.

BUILD FAILED
```

## Install
```
npm install react-native-device-settings --save
```

### Automatic Install
```
react-native link react-native-device-settings
```
### Manual Install

### `iOS`

-NA: using Linking RN library. URLs applicable for IOS 10.

### Android

1. In `settings.gradle`, insert the following code:
    ```
    include ':react-native-device-settings'
    project(':react-native-device-settings').projectDir = new File(settingsDir, '../node_modules/react-native-device-settings/android')
    ```

2. In `build.gradle`, insert the following code:
    ```
    android {
      ...
    }
    ...

    dependencies {
      ...
    + compile project(':react-native-device-settings')
    }
    ...
    ```
3. Edit `MainActivity.java` to look like this

    ```
    ...

    import com.rjblopes.opensettings.OpenSettingsPackage; // <-- add this import
    ...
    ```

## Usage

```javascript

import DeviceSettings from 'react-native-device-settings';

// Open settings menu
DeviceSettings.open();

// Open app settings menu
DeviceSettings.app();

// Open wifi settings menu
DeviceSettings.wifi();
```


## Dev Notes
Developed for personal use and might be useful for others.
