---
{"dg-publish":true,"permalink":"/First App Setup/","tags":["coding"]}
---


---
# First App Setup
> The Setup procedure for the first ever React App I make using [[React Native\|React Native]] CLI & a wired USB connection instead of [[Expo\|Expo]]. Setup taught partially by Hitesh (Chai aur Code) and partially learnt from the [React Native Documentation](https://www.reactnative.dev)

The first step is to complete the [[React Native Installation Guide\|React Native Installation Guide]].
From there, we need to plug in the phone in the PC or laptop using a USB cable and use the extra  `lsusb` command in the terminal to see the device ID of our phone. Whenever in doubt, disconnect & run the command again. Compare the two lists. The missing device is your phone.

Once we do that, we need the first 4 digits of our phone's Device ID as shown by `lsusb` command.

For Example: My Samsung M32 5G has the Device ID: `04e8:6860` i.e., the first four digits are: `04e8`

Follow [this page](https://reactnative.dev/docs/getting-started-without-a-framework) if you are NOT going to use Expo.

***==Keep in mind to keep developer options & USB debugging enabled.==***

Here is the command used to create the app: 
`npx @react-native-community/cli@latest init AwesomeProject`

To start your app, use the command:
`npm start android` or `npm start ios` depending upon which phone you have connected to the coding device where the app code resides.

---
# Footnotes