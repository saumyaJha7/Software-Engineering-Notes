---
tags:
  - expo-router
  - navigation
  - react-native
  - expo
---
## File Based Routing ( like next.js ) build on top of react navigation 


1. All the latest updates :- https://docs.expo.dev/router/introduction/
2. All the major things to know :- https://gregarious-gray-075.notion.site/Expo-Router-101-363c3158e38d80bfa9b0c12366a3479a



## Summary :- 

| Pattern         | File Name        | Matches                                            |
| --------------- | ---------------- | -------------------------------------------------- |
| Static route    | `about.tsx`      | `/about`                                           |
| Index route     | `index.tsx`      | `/` or folder root                                 |
| Dynamic segment | `[id].tsx`       | `/123`, `/abc`                                     |
| Catch-all       | `[...slug].tsx`  | `/a/b/c`                                           |
| Layout          | `_layout.tsx`    | Wraps children ( isme hi saara navigators setup )  |
| Route group     | `(group)/`       | No URL change                                      |
| Not found       | `+not-found.tsx` | Unmatched routes                                   |


#### Example for Layout :- 

```
app/
├── _layout.tsx           ← Root Stack layout
└── (tabs)/
    ├── _layout.tsx       ← Tabs layout
    ├── index.tsx         → Home tab
    ├── explore.tsx       → Explore tab
    └── profile.tsx       → Profile tab
```

```jsx
// app/(tabs)/_layout.tsx
import { Tabs } from 'expo-router';

export default function TabLayout() {
  return (
    <Tabs>
      <Tabs.Screen name="index"   options={{ title: 'Home' }} />
      <Tabs.Screen name="explore" options={{ title: 'Explore' }} />
      <Tabs.Screen name="profile" options={{ title: 'Profile' }} />
    </Tabs>
  );
}
```

  



## For protected routes and role based access :- 


- read notion notes .. 


#### Basic example : 
```jsx
// app/(tabs)/_layout.tsx
import { Tabs } from 'expo-router';

export default function TabLayout() {
  const { isAdmin } = useAuth();  // or whatever hook ya authContext etc 

  return (
    <Tabs>
      <Tabs.Screen name="index" options={{ title: 'Home' }} />
      <Tabs.Screen name="explore" options={{ title: 'Explore' }} />

      {/* Tab only visible to admins */}
      <Tabs.Protected guard={isAdmin}>
        <Tabs.Screen name="admin" options={{ title: 'Admin' }} />
      </Tabs.Protected>
    </Tabs>
  );
}
```



## Also layouts mai ek chiz hoti hai slot .. it is like placeHolder .. jo bhi active screen hogi wo show kr denge .. and uske alawa kch aur dikhana hai to wo bhi 

```jsx
import { Slot } from "expo-router";
import { Text } from "react-native";
import { SafeAreaView } from "react-native-safe-area-context";

export default function RootLayout() {
  return (
    <SafeAreaView style={{ flex: 1, alignItems: "center" }}>
      <Text>Header</Text>
      <Slot />
      <Text>Footer</Text>
    </SafeAreaView>
  );
}
```




## Also there are three types of tabs implementation we can do :-

1. Js tabs : jo by default abhi tak implement krte hai ( read more in notion )
2. Native tabs : iPhone ke liye alg and android ke liye alg ( as of july 2026 in beta )
3. Custom Tabs : khud kch bna lo 