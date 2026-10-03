# React Native

## Expo

### Create App

```bash
npx create-expo-app@latest
```

### Reset Project

```bash
npm run reset-project
```

### Install Expo Dev Client

```bash
npx expo install expo-dev-client
```

### Install Dependencies

```bash
npm install
```

### Start Development Server

```bash
npx expo start
```

### Run Android

```bash
npx expo run:android
```

### Run iOS

```bash
npx expo run:ios
```

---

## Expo Development Build

Install the development client:

```bash
npx expo install expo-dev-client
```

Create and run a development build:

### Android

```bash
npx expo run:android
```

### iOS

```bash
npx expo run:ios
```

Start the development server:

```bash
npx expo start --dev-client
```

---

## Expo Production Build

Build a production app using EAS:

### Install EAS CLI

```bash
npm install -g eas-cli
```

### Login

```bash
eas login
```

### Configure EAS

```bash
eas build:configure
```

### Android Production Build

```bash
eas build --platform android
```

### iOS Production Build

```bash
eas build --platform ios
```

### Android + iOS

```bash
eas build --platform all
```

---

## React Native CLI

### Create App

```bash
npx @react-native-community/cli@latest init MyApp
```

### Enter Project

```bash
cd MyApp
```

### Start Metro

```bash
npx react-native start
```

### Run Android

```bash
npm run android
```

or:

```bash
npx react-native run-android
```

### Run iOS

```bash
npm run ios
```

or:

```bash
npx react-native run-ios
```

---

## Android

### Check Connected Devices

```bash
adb devices
```

### Android SDK Configuration

File:

```text
android/local.properties
```

```properties
sdk.dir=/Users/anupjaiswal/Library/Android/sdk
```

### Clean Android Build

```bash
cd android
./gradlew clean
cd ..
```

---

## Prerequisites

```text
Node.js
JDK
Android Studio
Xcode
```

### Check Node.js

```bash
node -v
```

### Check Java

```bash
java -version
```
