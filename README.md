# Android-Firebase
connect Firebase services

## Requirements

1 -  ``` multiDexEnabled true ```
on app gradle defaultConfig

2 - Download "xFirebase.zip" and Import as module
https://cdn.xtsmm.com/android/libraries/Android%20Ads.zip

3 - add in app gradle 
```
implementation project(path: ':xFirebase')
```

4 - Connect to Firebase in android Studio

```
implementation 'com.google.firebase:firebase-analytics:18.0.0'
implementation 'com.google.firebase:firebase-auth:20.0.1'
implementation 'com.google.firebase:firebase-firestore:22.0.0'
implementation 'com.google.firebase:firebase-storage:19.2.0'
implementation 'com.google.firebase:firebase-messaging:21.0.0'
implementation 'com.google.firebase:firebase-config:20.0.1'
implementation 'com.google.firebase:firebase-dynamic-links:19.1.1'
implementation 'com.google.firebase:firebase-appindexing:19.1.0'
implementation 'com.google.firebase:firebase-inappmessaging-display:19.1.2'
```
