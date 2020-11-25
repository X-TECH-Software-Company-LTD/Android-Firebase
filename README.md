# Android-Firebase
connect Firebase services

## Requirements

1 -  ``` multiDexEnabled true ```
on app gradle defaultConfig

2 - add dependencies to app gradle 

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

3 - Connect to Firebase in android Studio (shortcut below)
```
Tools -> Firebase -> Analytics -> Log an Analytic Event -> Connect to Firebase
```
