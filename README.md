# Android-Firebase Standard App
connect Firebase App services

## Available Methods

1. Analytics
2. Cloud Messaging
3. In App Messaging

## Requirements

1 -  ``` multiDexEnabled true ```
on app gradle defaultConfig

2 - add dependencies to app gradle 

```
implementation 'com.google.firebase:firebase-analytics:18.0.0'
implementation 'com.google.firebase:firebase-messaging:21.0.0'
implementation 'com.google.firebase:firebase-inappmessaging-display:19.1.2'
```

3 - Connect to Firebase in android Studio (shortcut below)
```
Tools -> Firebase -> Analytics -> Log an Analytic Event -> Connect to Firebase
```

4 - Download "xFirebase1.zip" , extract and copy.

5 - Right Click on your MainActivity in Android Studio and select "Show in Explorer" , paste them.

6 - [for Cloud Messaging]
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

## Firebase Analytics

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
