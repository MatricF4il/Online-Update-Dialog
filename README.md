# 🚀 APK Injection Guide — MF Online Dialog

Follow these steps to professionally inject the Update Dialog into any APK.

---

## 📂 Step 1: File Setup
1. **Decompile your APK** using MT Manager, NP Manager, or APKTool.
2. **Add Assets:**
   - Copy ` ` and `  ` into the `assets/` folder of the APK.
   - Create a file named `ㅤㅤㅤㅤ` (four spaces) in the `assets/` folder.
   - Open the **Firebase Admin Panel**, enter your Firebase URL, and copy the **Encrypted Asset Content**.
   - Paste that content into the `assets/ㅤㅤㅤㅤ` file.

3. **Add DEX:**
   - Inject `classes_.dex` into your APK. If using MT Manager, just add it as a new DEX file (e.g., `classes2.dex` or `classes3.dex`).

---

## 🛠️ Step 2: Manifest Permissions
Open `AndroidManifest.xml` and ensure these permissions are present:
```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

---

## 💉 Step 3: Smali Injection
1. Locate your **Main Activity** (e.g., `MainActivity.smali`).
2. Search for the `onCreate` method:
   `.method public onCreate(Landroid/os/Bundle;)V`
3. Paste the following line right after `super.onCreate()`:

```smali
invoke-static {p0}, Lcom/android/mf/ㅤ;->showUpdateDialog(Landroid/app/Activity;)V
```

---

## 🌐 Step 4: Firebase Admin Panel
1. Open `firebase-admin-panel.html` in any text editor.
2. Enter your **Firebase Realtime Database URL** in JavaScript then save.
3. Customize your dialog (Title, Subtitle, What's New, Link).
4. Click **"Push to Firebase"**.
5. Your app will now automatically show the dialog based on your Firebase settings!

---

## 📢 Support & Updates
Join our Telegram for more professional tools and updates:
👉 [**Telegram: @Matric_F4il**](https://t.me/Matric_F4il)

*Created with ❤️ by Matric F4il*
