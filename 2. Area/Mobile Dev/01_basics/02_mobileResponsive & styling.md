---
tags:
  - mobileDev
  - react-native
  - expo
---

# Styling :- 


- no css , browser hence no css engine 
- RN uses styleSheet


### 1. StyleSheet.create() : used to create styles , so that code readable bne


### 2. .compose() : Do style ko merge krne ke kaam aata hai 

==But generally better way is to use array , coz usme conditionally bhi render kr skte hai ==

```js
<Text style={[
	styles.text,  // by default isme color black 
	isRed ? styles.redText : null
]}>styling</Text>
```



### 3. .flatten() : two styles ka mila ke ek obj 

```js
const flattenStyles = StyleSheet.flatten([styles.text, styles.redText])

<Text style={flattenStyles}>styling</Text>
```




## Hooks for responsive designs  :- 

1. useWindowDimensions
2. useColorScheme




### 1. useWindowDimensions 

- it is a hook that provides 4 values : h , w , scale , fontScale of the device 
- isse harr device p hamari app will be consistent in height 
- as fixed w or h may break in certain devices 

```js
const { height , width , scale , fontScale } = useWindowDimensions();
```

```js
width : 400    // may good for some but may break for other devices 


width : width * 0.5   // consistent 
```

#### Also we can use it for portrait vs landscape view 

```js
 <Text>
	 { height > width ? "Portrait" : "Landscape" }
</Text>
```




### 2. useColorScheme 

- this provides mobile's theme preference 


```js
import { useColorScheme } from "react-native";

const theme = useColorScheme();

<Text
	style={{
		color: theme === "dark" ? "white" : "black",
	}}
>Light Dark Mode</Text>
```


