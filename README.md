# Android-Firebase Analytics and Messaging
connect Firebase services

## Available Methods

1. Analytics
2. Cloud Messaging
3. In App Messaging

## Requirements

1 -  ``` multiDexEnabled true ```
on app gradle defaultConfig

2 - add Permissions to Manifest
```
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
<uses-permission android:name="android.permission.ACCESS_WIFI_STATE" />
```

3 - add dependencies to app gradle 

```
implementation 'com.google.firebase:firebase-analytics:18.0.0'
implementation 'com.google.firebase:firebase-messaging:21.0.0'
implementation 'com.google.firebase:firebase-inappmessaging-display:19.1.2'
```

4 - Connect to Firebase in android Studio (shortcut below)
```
Tools -> Firebase -> Analytics -> Log an Analytic Event -> Connect to Firebase

// For Cloud Messaging
click on Add FCM to your App
```

5 - Download "xFirebase1.zip" , extract and copy.

6 - Right Click on your MainActivity in Android Studio and select "Show in Explorer" , paste them.

7 - [for Cloud Messaging] , add in Manifest inside Application tag
```
<service
android:name=".xFirebaseMessagingService"
android:exported="false">
  <intent-filter>
    <action android:name="com.google.firebase.MESSAGING_EVENT" />
  </intent-filter>
</service>
```

# Usages 

## 1 - Firebase Analytics

Start Analytics (standard)
```
xFirebase xfirebase=new xFirebase(this);
xfirebase.startAnalytics();
```

Log an Event (advanced)
```
JSONArray JsonArray = new JSONArray();
JSONObject JsonObject = new JSONObject();
try {
  JsonObject.put("name", "value");
  JsonObject.put("click", "shopping");
} catch (JSONException e) {
  e.printStackTrace();
}
JsonArray.put(JsonObject);
xFirebase xfirebase=new xFirebase(this);
xfirebase.logAnalytics(JsonArray);
```

## 2 - Firebase Cloud Messaging

Tools -> Firebase -> Set Up Firebase Cloud Messaging -> Connect to Firebase

Send Notifications at firebase https://console.firebase.google.com/

### Cloud Messaging (standard)
```
Do not require any code to accept Messages.
Notifications will be shown Automatically.
Fixed foreground / background Notification problem.
```

### Cloud Messaging with Parameters (advanced) or
### Android Notifications with Button (on foreGround)

this advanced method is to send notification with " custom data ". Additional options from firebase.
This method will create buttons on notification with specific instructions. for example : to open MainActivity or A URL to browser.

![Firebase Setting](https://cdn.xtsmm.com/android/images/Capture.PNG)

Key ``` #button.Open|MainActivity.class ```

1. #button = require
2. .Name = Text on Button
3. |MainActivity.class = Class Name to Go
4. |https://www....com/url = URL to Go

Value ``` { a:1,b:2,c:3} ```

JSON data format, object data , support only 1 key and 1 value sepatered by coma.

### Listen action data on Button Click
```

new xFirebase(this).notificationActions(new actionOnNotification() {
@Override
public void onData(JSONObject object) {
  Log.d("xTechLog",object+"");
}
});
```

### Listen data from Notification


