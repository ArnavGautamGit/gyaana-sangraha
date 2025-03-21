---
{"dg-publish":true,"permalink":"/React Native Styling & Layout/","tags":["coding"]}
---


---
# React Native Styling & Layout
- Inline Styles in tags like CSS are also available in React Native `<View style ={{ backgroundColor: 'blue', flex: 1}}>Hello World</View>`
- Declaring styles as objects 
```React
<View style={ViewStyles}>
</View>

const ViewStyles = {
backgroundColour: 'blue',
color: #fff,
};
```
- Stylesheet Creation
```React
const styles = Stylesheet.create({
	container: {
	flex: 1,
	justifyContent: 'center',
	alignItems: 'center',
	},
	welcome: {
	fontSize: 20,
	textAlign: 'center',
	margin: 10,
	},
})
```
- Use `borderWidth: Stylesheet.hairlineWidth` for a VERYYY thin border around the object!
## Box & Flexbox Model
- Flexbox is enabled by default, cannot be changed
- Flex Direction is column by default, can be set to row
- Margin and padding are same as CSS.
- `borderRightWidth` and `borderLeftWidth` exist but top and bottom do not.


---
# Footnotes