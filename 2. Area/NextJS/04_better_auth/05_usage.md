---
tags:
  - next
  - better-auth
  - auth
---
#### https://better-auth.com/docs/basic-usage



### - create a simple login page and two buttons for google and github 


## - just add these two lines of code for bare minimum thing :- 

```js
await authClient.signIn.social({
      provider: "google",
      callbackURL: "/dashboard",
    });
```


## - also can get the session ( user data ) 

	- Frontend checks :- 
	

```js
const { data: session } = await authClient.getSession()

if (!session) {
    return (
      <>
        Please login first{" "}
      </>
);

return ( <> User name is : {session.user.name}</>)
```

## - can signout ( authClient/signOut() )




# How to protect routes like :- 


- user login nai hai to by-default koi bhi page visit krne jaaye to re-direct ho jaye "/login p"
- login hai to dubara "/login " p na jaa paaye 

### yaha ek problem hai k login page to client component hai but route protect krna hai aise to server chahiye ... 

#### Soln : ek dusra component bna lo ( client compo )and main login page mai load krlo ( ye apna normal server compo ) and write the logic 


# 🔐 Route Protection (Core Concept)

In ==server== components / API:

```js
import { auth } from "@/lib/auth";
import { headers } from "next/headers";
import { redirect } from "next/navigation";
  
export default async function Home() {
  const session = await auth.api.getSession({
    headers: await headers(),
  });

  if (!session) {
    redirect("/login");
  }
  
  return (
    <>
    Home Page
    <>
  );
}
```