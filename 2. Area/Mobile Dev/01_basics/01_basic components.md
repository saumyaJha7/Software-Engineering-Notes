---
tags:
  - mobileDev
  - react-native
  - expo
---


## 1. Pressable  

- onLongPress
- onPressIn
- special styling based on press or not 

```jsx
style = { ({pressed})  =>  ({
		backgroundColor : pressed ? "red" : "green"
	})
}
```




## 2. ScrollView : scrollable view 

- now view is scrollable 
- but , loads all item at once 
- performance overhead , not good for large data 
- use for small data 




## 3. FlatList : performance optimised scrollView 

- only loads what's visible +- thoda aage piche ka bas 
- good for large lists 



```jsx
<FlatList  
	data={users}   // array 
	renderItem={({ item }) => (  // How each item looks.
		<Text>{item.name}</Text>  
	)}  
	keyExtractor={(item) => item.id}  // key for performance 
/>
```






## 4. KeyboardAvoidingView

- for avoiding keyboard overlap.
- eg : wtsp chat p type krne jao to msg input box keyboard ke upar aa jata hai 


```jsx
 <KeyboardAvoidingView
    style={{
        flex: 1,
        justifyContent: "flex-end",
    }}
         behavior={Platform.OS === 'ios' ? 'padding' : 'height'}  // imp
         keyboardVerticalOffset={80} // for extra space 
    >
        <TextInput
        placeholder="Type here..."    
        style={{ borderWidth: 1, borderColor: "gray", padding: 10, margin: 20 }}
        />
    </KeyboardAvoidingView>
```




## 5. SafeAreaView : "not all screen is safe to use"

- iphone top notch 
- status bar ( upar wala ) + nav/home bar ( niche )
- curved display 

-- in sab ki wajah se top side ka content may hide behind them 

#### Solution : use SafeAreaView 

- wrap the screen in this SAView and done 
- easy , automatic , great for most apps 


```jsx
<SafeAreaView style={{ flex: 1 }}>  
	<Text>Profile</Text>  
</SafeAreaView>
```



## 6. useSafeAreaInsets() hook : same problem 

- ye hook 4 readOnly value de deta hai phone ke according 
- like top , botton , right , left ( this tells kitna padding rkhna hai to be in safe area )

- used for more customisation 
- manual control , adv layouts 

```jsx
const insets = useSafeAreaInsets();


<View  
	style={{  
		paddingTop: insets.top,  
	}}  
> 					 
	<Text>Hello</Text>  
</View>
```


## ==Imp note : RN se nai import krna hai wo deprecated hai rather do this ==

```js
import {
  SafeAreaView,
  useSafeAreaInsets
} from "react-native-safe-area-context";
```

