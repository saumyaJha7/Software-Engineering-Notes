---
tags:
  - thinking
  - backend
  - assignment
  - actualLearning
---


# Task 1 : Create Playlist 

- get the details 
- validate name coz it is req ( desc optional hai )
- create a playlist doc with owner 
- videos field abhi kch nai pass krenge 
- return res


# Task 2 : Get/Read playlist by Id

- get the Id 
- check proper mongoose id hai n 
- playlist model mai find kar 
- nai aaya to error
- return res


# Task 3 : Update playlist

- get the playlistId and validate
- get the data and validate name 
- findByIdAndUpdate
- handle null and return res


# Task 4 : Delete playlist 

- get the id and validate 
- findByIdAndDelete
- handle null and return 


# Task 5 & 6 : Add & Remove video to playlist 

- get both the ids and valid using mongoose 
- update the playlist model by pushing one video to it ( addToSet to prevent duplicate )
- ==also match owner as well==

## Same for remove ( just use $pull instead of $addToSet )


# Task 6 : get user Playlists

- get the user id
- validate with mongoose 
- Playlist mai find krlo where owner == userId 
- populate krlo vidoes and get the req fields only 
- ==array short hai kyuki playlist get kr rhe not whole videos  isliye populate bhi chalega .. simple hai==

