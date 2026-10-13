---
tags:
  - backend
  - mongo
  - aggregate
---
## Detail convo about why and practical cases  : https://chatgpt.com/share/693a6d2c-f874-800f-b502-21502d8a62d7



# Now we want to get the watch history :- 


```
subPipeline is needed coz nested refn hai models ka ... like users ko join krenge videos se phir bhi owner Id hi hoga to usko bhi calculate krna pdega nd uske liye join krna pdega again .. 
```


### so , step 1 :- 

```js
const history = await User.aggregate([
    {
      $match: { _id: new mongoose.Types.ObjectId(req.user._id) },
    },
    {
      $lookup: {
        from: "videos",
        localField: "watchHistory",
        foreignField: "_id",
        as: "history",
      },
    },
  ]);
```

### This just returns :- 

```js
[
  {
    _id: ObjectId("..."),
    userName: "alice",
    email: "alice@example.com",
    watchHistory: [ ObjectId("v1"), ObjectId("v2") ],
    history: [
      {
        _id: ObjectId("v1"),
        title: "Video 1",
        thumbnail: "...",
        duration: 120,
        views: 1000,
        owner: ObjectId("ownerId1"),   // this is the problem
        createdAt: ISODate("..."),
        // ...other video fields
      },
      {
        _id: ObjectId("v2"),
        title: "Video 2",
        owner: ObjectId("ownerId2"),
        // ...
      }
    ],
  }
]

```


## Step 2 :-    get the owner details .. 

```js
const history = await User.aggregate([
    {
      $match: { _id: new mongoose.Types.ObjectId(req.user._id) },
    },
    {
      $lookup: {
        from: "videos",
        localField: "watchHistory",
        foreignField: "_id",
        as: "history",
        pipeline: [
          {
            $lookup: {
              from: "users",
              localField: "owner",
              foreignField: "_id",
              as: "videoOwner",
            },
          },
        ],
      },
    },
  ]);
```

### What this returns is :- 

```js
[
  {
    _id: ObjectId("..."),        // the user
    userName: "...",
    email: "...",
    watchHistory: [ObjectId("v1"), ObjectId("v2")],
    // other user fields...
    history: [
      {
        _id: ObjectId("v1"),
        videoFile: "...",
        thumbnail: "...",
        title: "...",
        duration: 123,
        views: 456,
        owner: ObjectId("ownerId1"),   // original owner field still present
        // other video fields...
        videoOwner: [
          {
            _id: ObjectId("ownerId1"),
            userName: "ownerName",
            fullName: "Owner Fullname",
            email: "owner@example.com",
            avatar: "...",
            // entire user document fields unless projected away
          }
        ]
      },
      {
        _id: ObjectId("v2"),
        // ...
        videoOwner: [ /* owner user doc */ ]
      }
    ]
  }
]

```



## Yahi to chahiye tha , isliye subPipeline needed hai ... bas ab ache se project krke , object bna ke return krdo 

- SBSE PHLE USER MAI AGGREGATE LAGAYA HAI TO JOIN IT WITH VIDEOS , THEN VIDEOS KE ANDAR AGAIN USER .. thoda smjh iss baat ko phir smjh aayga project konsa kaha lgega 
- dhyan rkhna konsa pipeline kiska hai
- kaha kya return ho rha hai 
- array ko object mai kr lena .. step by step
- owner ya watchHistory ko hi overWrite kr le 


# IMP NOTE :- 

```js
const userId = req.user._id 
```
## What is userId ? 
## Ans : It is a string ... 

```js
const userId = new mongoose.Types.objectId(req.user._id)
```
## Now ?
## Ans : ab ye mongoDB mai jaise store hota hai wo ID hai


## **"Generally mongoose isko convert kr deta hai but aggregation pipeline mai hamko khud hi krna pdta hai"**
