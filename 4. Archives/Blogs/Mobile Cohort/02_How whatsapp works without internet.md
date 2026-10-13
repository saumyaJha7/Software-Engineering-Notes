---
tags:
  - blog
  - react-native
---
Imagine a scenario , you are chating with someone and suddenly the internet goes off . 

What do you think will happen to your messages ?

If they disappear or the app crashes , it is not a good user experience . 



But in reality , apps are made keeping in mind these types of edge cases , therefore they are made offline first . 

  

## But what exactly does offline-first mean? 

Okay , let’s analyse the situation .

  

#### First of all What happens when you send a message without internet ?

Ans) WhatsApp uses offline first approach that is , it stores your action ( like sending a message ) into the local storage of the device first despite of the network condition .

**This also explains why your message appears instantly in the chat, even when you are offline.** Since the app first saves the message in local storage and immediately renders it on the screen, the user gets instant visual feedback. The network communication happens in the background, making the app feel fast and responsive even if the message hasn't reached the server yet.



![[Pasted image 20260728183903.png]]


1. user A does an action ( like sending a message to user B ) 
2. app stores the data immediately to local storage first .
3. Now , the app checks whether connection to server is possible or not .
4. If connected, it sends the message to the server .
5. If not connected, the message simply remains in the local queue until connectivity returns.


#### Now another question that might come to your head is , But what exactly is local storage? 

In a very simple term , local storage is a storage area of the user’s device where the app can save data even without an internet connection .
And the data is stored persistently on the device that means even if the user closes the app , data is still there .


So let’s move forward and take a look at the flow of the local storage in both the situations listed below , 

1. When user does some action internet was there .
2. When user does some action , no interent .

  

So case 1 , when internet is there :

- user does some action 
- app saves the data in local storage 
- app tries to reach the server 
- it successfully reaches the server 
- data is sent to the server

  

And in case 2 , when there is no interent , 

- user does some action 
- app saves the data in local storage 
- app tries to reach the server 
- app fails to reach to the server 
- app stores the pending action into the queue


![[Pasted image 20260728185120.png]]


Now , what happens when the interent comes in the 2nd case :- 

1. app detects that internet connectivity is restored.
2. It checks the local queue for any pending messages/actions.
3. It sends the pending messages to the sever in FIFO order.
4. The server acknowledges (confirms) that it has received each message.
5. Once acknowledged, the app removes that message from the pending queue and updates its status.



## Delivery States 

So while all this is happening whatsapp does one more thing , every message maintains a state called delivery state .


Imagine that you are texting with your friend , and the internet goes off , now the message that you sent after it cannot be sent to the server so it is just stored in the local queue . 

##### This is pending state.

  

So , pending state is when : 

- message saved locally
- waiting in queue
- all is local , server has never seen it .

  

After the pending state comes the sent state , it is when the internet is there on the sender’s side and the message has been sent to the server after storing in the local storage .

One important thing to notice , sent state does not mean your friend has received the message it means that data is sent from your app to the server and the server has received the message . 

  

Now , after receiving the message from user A ( you ) , the server tries to contact the user B ( your friend ) and when it contacts successfully & sends message successfully , it is called delivered state . 

In this state , data is delivered from user A to user B . 

  

And the final state is read state , as the name suggests it is the state of message transfer when the user B reads the message sent from user A .



## Handling media files 

Text messages are small, but media files introduce another challenge.

  

A media file (image, video, document) is very different from a text message.

A text message might be just a few bytes , but a video file can be of 100 mb.

Storing them directly into the local database is inefficient .

  

Instead, apps usually:

1. Save the media file in the device’s file system.
2. Store **metadata** in local storage/database.

  

For example : 

Message ID: 101  
Type: Image  
File Path:  
/storage/chat/image101.jpg  
Status: Pending Upload

Notice that the database isn’t storing the image itself.

It’s storing information **about** the image.

  

### What happens while offline?

Suppose you’re on airplane mode.

You select an image.

The app:

1. Saves the image on the device (file system).
2. Creates a pending upload entry in the local database/queue.
3. Shows the image immediately in the chat.
4. Displays a pending (clock) status.
5. Waits for connectivity.

When internet returns:

- The queue reaches this pending upload.
- The app uploads the file to the server.
- The server confirms it.
- The message status changes.



### Message Ordering and Conflict Resolution

Imagine you and your friend are both offline. While disconnected, both of you send multiple messages. Once connectivity is restored, the server receives messages from both devices and merges them into a single conversation.

To keep the chat consistent, messaging apps maintain the order of pending messages (using FIFO on the client side) and use timestamps or message IDs on the server to display messages in the correct sequence. This ensures that both users eventually see the same conversation history.

  


## Reliability 
All of these mechanisms—local storage, queues, synchronization, and delivery states—exist for one primary reason: reliability.

A reliable messaging app should preserve user actions, retry failed operations automatically, clearly show message status, and avoid losing data, so users can trust the application even with poor connectivity.



  

# Conclusion : 

At first glance, it may seem like messaging apps simply stop working without an internet connection. However, the reality is quite different. Modern messaging apps like WhatsApp follow an **offline-first architecture**, where every user action is first stored locally instead of depending entirely on the network.

This approach ensures that your messages don’t disappear even if the internet goes off or the app restarts. Pending messages are safely stored on the device, organized in a queue, and automatically synchronized with the server once connectivity is restored. Throughout this process, delivery states such as **Pending**, **Sent**, **Delivered**, and **Read** keep users informed about the current status of their messages.

One important concept behind this design is **eventual consistency**. When you’re offline, your device and the server may not have the same data. However, once the network is available again and synchronization completes, both eventually reach the same state. This allows users to continue chatting naturally without worrying about temporary network issues.

Like every design choice, offline-first architecture comes with trade-offs. While it greatly improves reliability and user experience, it also introduces challenges such as maintaining message order, handling conflicts, managing media uploads, and ensuring proper synchronization. Despite this added complexity, the result is a messaging experience that feels fast, reliable, and seamless — even on unstable internet connections.

In the end, the reason WhatsApp feels so responsive is not because it always has an internet connection, but because it is designed to work intelligently even when it doesn’t.