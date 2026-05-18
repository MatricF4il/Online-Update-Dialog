# Online Update Dialog Injection Guide

**For Educational & Testing Purposes Only.**

This guide provides comprehensive instructions for integrating a custom online update dialog into Android Package Kits (APKs). The system allows for dynamic management of update notifications, version control, and download links via a Firebase-powered administration panel.

---

## Project Overview

The project consists of a zipped package named `online_update_dialog.zip` which contains the following essential components:

*   `assets/` folder: This directory holds three files with invisible names. Two are image assets used within the update dialog, and one contains the encrypted Firebase URL.
*   `classes_.dex`: A DEX file (or `classesX.dex` where `X` is a number) containing the core logic for the update dialog.
*   `URL_Encrypter.html`: An HTML utility for encrypting Firebase URLs.
*   `Firebase_Admin_Panel.html`: An HTML-based administration panel for managing update dialog content.

---

## Setup and Integration Guide

Follow these steps to successfully integrate the online update dialog into your APK.

### Step 1: APK Decompilation and File Placement

1.  **Decompile your APK** using a suitable tool such as MT Manager, NP Manager, or APKTool.
2.  **Place `classes_.dex`:** Inject the `classes_.dex` file into your decompiled APK. If using MT Manager, add it as a new DEX file (e.g., `classes2.dex` or `classes3.dex`).
3.  **Add Assets:**
    *   Copy the two image files (with invisible names) into the `assets/` folder of your decompiled APK.
    *   Create a new file with four invisible characters as its name (e.g., `ã…¤ã…¤ã…¤ã…¤`) inside the `assets/` folder. This file will store your encrypted Firebase URL.

### Step 2: Firebase URL Encryption

1.  **Open `URL_Encrypter.html`** in a web browser.
2.  **Enter your Firebase Realtime Database URL** into the provided input field.
3.  The tool will automatically encrypt the URL and provide the encrypted content. Copy this **Encrypted Asset Content**.
4.  **Paste the copied content** into the `assets/ã…¤ã…¤ã…¤ã…¤` file (the one with four invisible characters) created in Step 1.

### Step 3: Firebase Admin Panel Configuration

1.  **Open `Firebase_Admin_Panel.html`** in any text editor.
2.  **Locate the JavaScript section** within the HTML file.
3.  **Insert your Firebase Realtime Database URL** into the designated variable within the JavaScript code. This URL should be the *unencrypted* Firebase URL.
4.  **Save** the `Firebase_Admin_Panel.html` file.
5.  **Open the modified `Firebase_Admin_Panel.html`** in a web browser. Your admin panel is now ready.
6.  From this panel, you can configure various aspects of the update dialog, including:
    *   Displaying/hiding the dialog.
    *   Setting the update message text.
    *   Specifying the new version number.
    *   Defining the file size (in MB).
    *   Providing the download link for the update.
7.  Click **"Push to Firebase"** to save your settings. Your application will now automatically display the update dialog based on these configurations.

### Step 4: APK Integration (Manifest Permissions & Smali Injection)

1.  **`AndroidManifest.xml` Permissions:** Open your `AndroidManifest.xml` file and ensure the following permissions are present:
    ```xml
    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```
2.  **Smali Injection:**
    *   Locate your **Main Activity** (e.g., `MainActivity.smali`) within the decompiled APK structure.
    *   Search for the `onCreate` method, typically defined as: `.method public onCreate(Landroid/os/Bundle;)V`
    *   Paste the following line of Smali code immediately after the `super.onCreate()` call:
        ```smali
        invoke-static {p0}, Lcom/android/mf/ã…¤;->showUpdateDialog(Landroid/app/Activity;)V
        ```

---

## Usage

Once integrated, your application will automatically check for updates and display the configured dialog based on the settings managed through the `Firebase_Admin_Panel.html`.

---

## Support

For support or inquiries, please contact the project maintainer.

---

*Created by JuTt*
