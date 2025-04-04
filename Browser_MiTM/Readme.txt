# Man-in-the-Browser Attack: API Hooking with DLL Injection

This project demonstrates a simple **Man-in-the-Browser (MitB)** attack using API hooking on Internet Explorer. It uses `hookdll.dll` to hook the `InternetReadFile()` API via DLL injection.

> ⚠️ **For educational purposes only. Do not use maliciously.**

---

## 🧩 Prerequisites

- Windows 10 (32-bit or 64-bit with 32-bit IE)
- Internet Explorer installed
- [RemoteDLL Tool](https://securityxploded.com/remotedll.php)
- `hookdll.zip` (Password: `infected`)

---

## 📌 Step-by-Step Instructions

### 1. Disable Internet Explorer to Edge Redirection

By default, Internet Explorer redirects to Microsoft Edge. To allow hooking in IE:
For that you need to disable loading of BHO(browser Helper Objects)
- Watch this tutorial to disable redirection:  
  📺 [Disable IE to Edge Redirection](https://www.youtube.com/watch?v=ERDkAhHw50M)


---

### 2. Inject the Hook DLL into Internet Explorer

Use the RemoteDLL tool to inject `hookdll.dll` into **Internet Explorer (32-bit)**.

- Path to IE (32-bit):  
  `C:\Program Files (x86)\Internet Explorer\iexplore.exe`

Steps:
1. Run RemoteDLL.
2. Select `iexplore.exe` from the process list.
3. Inject `hookdll.dll`.

> 🔁 Some web pages may cause IE to restart (respawn). You’ll need to **re-inject the DLL** or use a script to **automatically inject into all IE instances continuously**.

---

### 3. Hook Target: `InternetReadFile()`

The DLL hooks the `InternetReadFile()` API to intercept HTTP content read by Internet Explorer.

> ✅ Compatible only with 32-bit Internet Explorer.

---

### 4. Browse Pages Containing "I'm Feeling Lucky"

Try visiting the following pages using Internet Explorer **after DLL injection**:

- 📚 [Amazon - I'm Feeling Lucky](https://www.amazon.in/Im-Feeling-Lucky-Confessions-Employee-ebook/dp/B0057WLCTO)
- 🔍 [Google - I'm Feeling Lucky](https://www.google.com)

Observe any changes or effects caused by the hook.

---

## 🔁 Optional: Write a Continuous Injector

To avoid repeated manual injection:
- Write a simple program that monitors `iexplore.exe` instances.
- Injects the DLL into new instances automatically.

---

