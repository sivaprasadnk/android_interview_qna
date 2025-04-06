# Explain Activity in Android

### 📌 **Activities in Android**  

An **Activity** in Android represents a single screen with a user interface. It is one of the fundamental building blocks of an Android app and acts as an entry point for user interactions.  

---

## 🔹 **Key Characteristics of an Activity**  
1. **Represents a UI Screen:** Every Activity corresponds to a screen in the app.  
2. **Lifecycle Management:** Activities have a well-defined lifecycle managed by the Android system.  
3. **Navigation & Interaction:** Activities facilitate user navigation and interaction with the app.  
4. **Back Stack Management:** Android manages the Activity back stack to handle user navigation.  

---

## 🔹 **Activity Lifecycle**  
The Android system manages Activities through a lifecycle with various states:  

### 📌 **Activity States:**  
1. **Created** → When the Activity is first created.  
2. **Started** → Visible but not in the foreground.  
3. **Resumed** → The Activity is in the foreground and interacts with the user.  
4. **Paused** → Partially visible but not focused.  
5. **Stopped** → No longer visible but still in memory.  
6. **Destroyed** → The Activity is removed from memory.  

### 🔄 **Lifecycle Callbacks:**  
- `onCreate()` → Called when the Activity is created.  
- `onStart()` → Called when the Activity becomes visible.  
- `onResume()` → Called when the Activity comes to the foreground.  
- `onPause()` → Called when another Activity comes in front.  
- `onStop()` → Called when the Activity is no longer visible.  
- `onDestroy()` → Called before the Activity is destroyed.  

---

## 🔹 **Declaring an Activity**  
In `AndroidManifest.xml`, every Activity must be declared:  
```xml
<activity android:name=".MainActivity" />
```

---

## 🔹 **Starting a New Activity**  
To open a new Activity, use an **Intent**:  
```kotlin
val intent = Intent(this, SecondActivity::class.java)
startActivity(intent)
```

To pass data between Activities:  
```kotlin
intent.putExtra("KEY", "Value")
startActivity(intent)
```
Retrieve the data in the second Activity:  
```kotlin
val data = intent.getStringExtra("KEY")
```

---

## 🔹 **Types of Activities in Android**  
1. **MainActivity** → The first screen when an app launches.  
2. **Transparent Activity** → Uses a transparent theme for overlays.  
3. **Dialog Activity** → Shows an Activity as a dialog.  
4. **Fullscreen Activity** → Hides system bars for immersive mode.  

---

## 🔹 **Best Practices for Activities**  
✔ Use **Fragments** for better UI flexibility instead of multiple Activities.  
✔ Avoid **keeping large objects** in Activity memory.  
✔ Use **ViewModels** to persist UI state across configuration changes.  
✔ Follow the **Single Activity Architecture** where possible with Navigation Component.  

---

### 🚀 **Conclusion**  
Activities are an essential part of Android apps, handling user interactions and navigation. Managing their lifecycle properly ensures a smooth user experience and optimized app performance.  
