# 📱 Calorie Tracker — Android APK Build Guide

## Prerequisites
Install these on your computer before starting:

1. **Node.js** → https://nodejs.org (LTS version)
2. **Android Studio** → https://developer.android.com/studio
   - During install, make sure to include **Android SDK** and **Android Virtual Device**
3. **Java JDK 17** → https://adoptium.net

---

## Step-by-Step Instructions

### 1. Open a Terminal / Command Prompt
Navigate to the project folder:
```bash
cd calorie-tracker-app
```

### 2. Install Capacitor dependencies
```bash
npm install
```

### 3. Add the Android platform
```bash
npx cap add android
```

### 4. Copy your web app into the Android project
```bash
npx cap copy android
```

### 5. Open the project in Android Studio
```bash
npx cap open android
```
This will launch Android Studio automatically.

---

## Building the APK in Android Studio

Once Android Studio opens:

1. Wait for **Gradle sync** to finish (progress bar at the bottom)
2. Go to the menu: **Build → Build Bundle(s)/APK(s) → Build APK(s)**
3. Wait for the build to complete
4. Click **"locate"** in the notification that pops up at the bottom right
5. Your APK will be at:
   ```
   android/app/build/outputs/apk/debug/app-debug.apk
   ```

---

## Installing on Your Android Phone

### Option A – Direct Transfer
1. Copy `app-debug.apk` to your phone via USB or Google Drive
2. On your phone, go to **Settings → Security → Unknown Sources** → Enable
3. Open the APK file on your phone and tap **Install**

### Option B – ADB (USB Cable)
```bash
adb install android/app/build/outputs/apk/debug/app-debug.apk
```

---

## App Features That Work on Android
✅ Meal logging with name, calories, macros  
✅ Daily goals tracking  
✅ Progress bars  
✅ Photo upload from gallery  
✅ Camera capture  
✅ localStorage (data saved between sessions)  
✅ Date navigation  

---

## Troubleshooting

| Problem | Solution |
|---|---|
| `npx cap add android` fails | Make sure Android Studio + SDK are installed |
| Gradle sync error | In Android Studio: File → Invalidate Caches → Restart |
| Camera not working | Check app permissions in phone Settings |
| App crashes on launch | Try **Build → Clean Project** then rebuild |

---

## Project Files Structure
```
calorie-tracker-app/
├── www/
│   └── index.html        ← Your web app (do not rename)
├── capacitor.config.json ← App configuration
├── package.json          ← Dependencies
└── BUILD_GUIDE.md        ← This file
```

> To change the app name or ID, edit `capacitor.config.json` before running `npx cap add android`.
