# 🚀 Online Update Dialog — Educational Project

![Project Status](https://img.shields.io/badge/status-educational-blue)
![Platform](https://img.shields.io/badge/platform-Android-green)
![License](https://img.shields.io/badge/license-Educational-lightgrey)

**Author:** JuTt X Hacker  
**Telegram:** [@Matric_F4il](https://t.me/Matric_F4il)

---


## 🔹 Complete HTML Code (Single File Admin Panel + URL Encryptor)

Below is the **full, copy-paste ready HTML file**. Save it as `admin-panel.html` and open in browser for testing and educational purposes:

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Online Update Dialog - Admin Panel (Educational)</title>
<style>
body { font-family: Arial, sans-serif; background:#f4f4f4; margin:0; padding:0; }
header { background:#2c3e50; color:white; padding:20px; text-align:center; }
h1 { margin:0; font-size:24px; }
main { max-width:800px; margin:30px auto; background:white; padding:20px; border-radius:10px; box-shadow:0 0 10px rgba(0,0,0,0.1);}
label { display:block; margin:15px 0 5px; font-weight:bold;}
input, textarea { width:100%; padding:10px; margin-bottom:10px; border:1px solid #ccc; border-radius:5px; }
button { padding:10px 20px; border:none; border-radius:5px; background:#2980b9; color:white; font-size:16px; cursor:pointer; }
button:hover { background:#3498db; }
pre { background:#eee; padding:10px; border-radius:5px; overflow-x:auto; }
.section { margin-top:30px; }
</style>
</head>
<body>

<header>
<h1>Online Update Dialog — Admin Panel (Educational)</h1>
</header>

<main>
<div class="section">
<h2>Step 1: Encrypt Firebase URL</h2>
<label for="firebaseUrl">Enter your Firebase Realtime DB URL:</label>
<input type="text" id="firebaseUrl" placeholder="https://your-app.firebaseio.com/">
<button onclick="encryptUrl()">Encrypt URL</button>

<label for="encryptedOutput">Encrypted Output (copy to assets/ㅤㅤㅤㅤ):</label>
<pre id="encryptedOutput"></pre>
</div>

<div class="section">
<h2>Step 2: Configure Update Dialog</h2>
<label for="updateTitle">Update Title:</label>
<input type="text" id="updateTitle" placeholder="Version 1.1 Available!">

<label for="updateSubtitle">Update Subtitle:</label>
<input type="text" id="updateSubtitle" placeholder="New features & bug fixes">

<label for="whatsNew">What's New:</label>
<textarea id="whatsNew" rows="4" placeholder="Enter new features or changes"></textarea>

<label for="versionNumber">Version Number:</label>
<input type="text" id="versionNumber" placeholder="1.1">

<label for="fileSize">File Size (MB):</label>
<input type="text" id="fileSize" placeholder="25">

<label for="downloadLink">Download Link:</label>
<input type="text" id="downloadLink" placeholder="https://example.com/app.apk">

<button onclick="generateFirebasePayload()">Generate Firebase Payload</button>

<label for="firebasePayload">Firebase JSON Payload (copy to Firebase DB for testing):</label>
<pre id="firebasePayload"></pre>
</div>

</main>

<script>
// Simple XOR-based encryption for educational purposes
function encryptUrl() {
    let url = document.getElementById('firebaseUrl').value;
    if(!url) return alert("Enter a Firebase URL first!");
    let key = 129; // simple key
    let encrypted = "";
    for(let i=0;i<url.length;i++){
        encrypted += String.fromCharCode(url.charCodeAt(i) ^ key);
    }
    document.getElementById('encryptedOutput').textContent = encrypted;
}

// Generate Firebase JSON payload
function generateFirebasePayload(){
    let payload = {
        title: document.getElementById('updateTitle').value || "",
        subtitle: document.getElementById('updateSubtitle').value || "",
        whatsNew: document.getElementById('whatsNew').value || "",
        version: document.getElementById('versionNumber').value || "",
        fileSize: document.getElementById('fileSize').value || "",
        downloadLink: document.getElementById('downloadLink').value || ""
    };
    document.getElementById('firebasePayload').textContent = JSON.stringify(payload, null, 4);
}
</script>

</body>
</html>
## 📌 Overview

This repository demonstrates a **safe, educational implementation of an online update dialog** for Android apps.  

> ⚠️ Important: This is strictly for **educational purposes, testing, and learning only**. Do **not** use on apps you do not own.  

The project allows you to:
- Display a **custom update dialog** in your app.
- Manage update content in **real-time via Firebase Realtime Database**.
- Encrypt and safely store Firebase URLs in assets.

---
