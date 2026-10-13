---
tags:
  - react-native
  - expo
  - navigation
  - react-navigation
---

```
react native : lib for building screens 

react navigation : lib for navigating between these screens 
```


# Read the docs  

- https://gregarious-gray-075.notion.site/Navigation-with-React-Navigation-361c3158e38d80c6988dc76f655b0059
- https://reactnavigation.org/docs/getting-started



### Installations :- 


```
npx create-expo-app -t blank-typescript   // for consistent plain ts template


npm install @react-navigation/native
npx expo install react-native-screens react-native-safe-area-context

// for stack 
npm install @react-navigation/native-stack
npm install @react-navigation/elements

// for tab 
npm i @react-navigation/bottom-tabs

// for drawer 
npx expo install react-native-gesture-handler react-native-reanimated 
npx expo install @react-navigation/drawer 
npx expo install react-native-worklets  

// read the docs for further info ya updated info 
```



## 2 type ke navigators setup hota hai :- 

- static : phle se sb configured rhta hai 
- dynamic : condition ke basis p screen show hogi ( eg user login hai to home screen else login screen )     ==more preferable==


#### thoda sa syntax ka change hota hai .. read about it in docs 




# And isme 3 type ke navigation hote hai :- 

https://chatgpt.com/g/g-p-69fd72aa379c8191afa95830f8ca4383-mobile-dev/c/6a509d89-5474-83ee-9628-949080c99143

1. Stack : ek screen ke upar dusri screen 
2. Tab : bottom tab buttons 
3. Drawer : side panel drawer


![[types of navigation in RN|900]]





## Some Ways to navigate using useNavigate hook :- 


- .navigate : normal switching 
- .replace : don't want user to return to earlier screen 
- .push : same screen multiple times 
- .goBack : previous screen
- .popTo(" ") / .popToTop : jumping multiple screens 
- useLinkTo/ Link paths → deep links + web URL navigation





### ==Also data bhi pass kr skte hai==

- for eg e-comm app hai .. saare products listed hai .. user clicks on specific product to uska detail page open hona chahiye ..


```
// product listing page   ->   details page  

navigation.navigate("Details" , { productId : p1 });
```

```ts
// details page 

function Details ({ route }) {
	const productId = route.params;
	
	return (
		<View>
			<Text>Product: {productId}</Text>
			<Button title="Open another Details" onPress={() => navigation.push('Details', { productId: 'p2' })} />
			
			<Button title="Back" onPress={() => navigation.goBack()} />
		</View>
	)
}
```


