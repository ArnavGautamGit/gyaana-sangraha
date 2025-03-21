---
{"dg-publish":true,"permalink":"/How to Install & Use Expo/","tags":["coding"]}
---


---
# How to Install & Use Expo
First, to check if it is already installed we can run the command:
```bash
expo --version
```

If the version number is displayed, that means it is installed.
Else if the terminal responds with "command not found", you will need to install Expo by running the command:
```bash
npm install -g expo-cli
```

Now you will be able to use [[Expo Commands\|Expo Commands]] globally.

This assumes that you have [[NodeJS\|NodeJS]] and [[Node Package Manager (NPM)\|Node Package Manager (NPM)]] already installed on your system.

Now, using the expo commands create your first app:
```bash
npx create-expo-app AppName
#swap "AppName" with the name of your app
```

---
### Testing Apps using ExpoGO
After this, from your phone, download the ExpoGO App from the Google Play Store or the Apple App Store. You will need to use the in-app QR code scanner to scan the QR on the terminal when you use `npm start` to run your app whenever you are testing it out.

Hitting `npm start` in the terminal will present to you the QR code, on scanning, it will give you a basic page and tell you that you need to run the following command to get a fresh start:
```bash
npm run reset-project
```

Now you are free to build your app! Installation and other processes are done!

---
# Footnotes

