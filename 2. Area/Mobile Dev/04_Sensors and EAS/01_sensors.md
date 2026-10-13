---
tags:
  - sensors
  - expo
---

## Sensors : hardware that detects physical properties .


### Now it is a hardware and js can't directly talk to it , so we need a bridge and that is expo-sensors .



Now before learning about different types of sensors , there is a common flow of it :- 

```
check availability  
subscribe to the data 
receive updates 
unsubscribe 
```


# So majorly 6 things we have to study :- 



#### 1.  Accelerometer  : that detects acc or motion along 3 dimensions .

#### 2. Gyroscope : angular velocity or rotation 

#### 3. Light sensors : detects light ( eg autoDarkMode , increaseBrightness etc )

#### 4. Magnetometer : detects magnetic field  of earth ( eg direction apps like maps  )

#### 5. Pedometer : detects steps ( eg fitness apps )
	- works on iOS , not good on android 
	- read about it in notion docs and gpt 


#### 6. Device motion : acc + gyro + magneto sensors 






## Read this :- 

- https://gregarious-gray-075.notion.site/Expo-Sensors-and-Device-Motions-Accelerometer-Gyroscope-LightSensor-36fc3158e38d808896b3dd119a363526
- https://gregarious-gray-075.notion.site/Expo-Sensors-and-Device-Motion-Magnetometer-Pedometer-DeviceMotion-371c3158e38d80129edbf438625af685#371c3158e38d80e485e6c7d1571293b4

