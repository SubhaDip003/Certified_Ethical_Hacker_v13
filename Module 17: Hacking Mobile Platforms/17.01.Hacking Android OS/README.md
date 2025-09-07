# 🤖 Hacking Android OS
Android is the most widely used mobile OS, but its open nature and unpatched vulnerabilities make it a common target for attackers. Many users do not update their devices, giving attackers chances to exploit flaws, install malware, or steal sensitive data. Threats include Android Trojans, rooting exploits, and hacking tools that compromise system security.

This section discusses the Android OS, its architecture, and the associated vulnerabilities. It also covers the process of rooting Android phones, rooting tools, Android Trojans, and hacking Android mobiles. Finally, the section discusses guidelines for securing Android devices, security controls, and device-tracking tools.

---
## Android OS 
🔗Source: [https://developer.android.com] <br>
Android, a software environment developed by Google for mobile devices, includes an OS, middleware, and key applications. The Android OS relies on the Linux kernel and is an open-source platform. 

**Features:**
- Provides a variety of prebuilt UI components such as structured layout objects and UI controls that allow one to build the GUI for the app
- Provides several options to save persistent application data:
  - Shared Preferences—Store private primitive data in key-value pairs
  - Internal Storage—Private data on the device memory
  - External Storage—Public data on the shared external storage
  - SQLite Databases—Store structured data in a private database
  - Network Connection—Store data on the web with your own network server
- RenderScript provides a platform-independent computation engine that operates at the native level. One can use it to accelerate apps that require extensive computational horsepower.
- Provides rich APIs that allow the app to connect and interact with other devices over Bluetooth, near-field communication (NFC), Wi-Fi P2P, USB, and session initiation protocol (SIP), in addition to standard network connections.
- Application framework allows for the reuse and replacement of components.
- Android runtime (ART) optimized for mobile devices.
- Integrated browser based on the open-source Blink and WebKit engine.
- SQLite for structured data storage.
- Media support for common audio, video, and still image formats (e.g., MPEG4, H.264, MP3, AAC, AMR, JPG, PNG, and GIF).
- Rich development environment including a device emulator, tools for debugging, memory and performance profiling, and a plugin for the Eclipse IDE.

---
## Android OS Architecture 
Android is a Linux-based OS designed for portable devices such as smartphones and tablets. It is a stack of software components categorized into six sections (System Apps, Java AP Framework, Native C/C++ Libraries, Android Runtime, Hardware Abstraction Layer (HAL), and Linux kernel) and five layers. 

The figure below shows a pictorial representation of the complete Android architecture: 

<p align="center">
  <img width="645" height="501" alt="image" src="https://github.com/user-attachments/assets/fd9a3348-e9cb-4acf-bc42-e11974d7689d" />
</p>

- **System Apps** <br>
  All Android system applications are at the top layer. Any app developed should fit into this layer. Some standard applications that come pre-installed with every Android device include dialer, email, calendar, camera, SMS messaging, web browsers, contact managers, and so on. Most Android apps are “written” in Java.

- **Java API Framework** <br>
  Android platform functions are made available to developers through APIs written in Java. The application framework offers many high-level services to applications, which developers incorporate in their development.
  Some of the application framework blocks are as follows:
  - **Content Providers** — Manages data sharing between applications.
  - **View System** — For developing lists, grids, text boxes, buttons, and so on.
  - **Activity Manager** — Controls the activity life cycle of applications.
  - **Location Manager** — Manages location using GPS or cell towers.
  - **Package Manager** — Keeps track of the applications installed on the device.
  - **Notification Manager** — Helps applications display custom messages in a status bar.
  - **Resource Manager** — Manages various types of resources used.
  - **Telephony Manager** — Manages all voice calls.
  - **Window Manager**  — Manages application windows.

- **Native C/C++ Libraries** <br>
  The next layer comprises the native libraries. Libraries are “written” in C or C++ and are specific to particular hardware. This layer allows the device to control different types of data. The native libraries are as follows:
  - **WebKit and Blink** — web browser engine to display HTML content
  - **Open Max AL** — companion API to OpenGL ES but used for multimedia (video and audio) rather than audio only
  - **Libc** — Comprises System C libraries
  - **Media Framework** — provides media codecs that allow recording and playback of different media formats
  - **Open GL | ES** — 2D and 3D graphics library
  - **Surface Manager** — meant for display management
  - **SQLite** — database engine used for data storage purposes
  - **FreeType** — meant for rendering fonts
  - **SSL** — meant for Internet security

- **Android Runtime** <br>
  It includes core libraries and the ART virtual machine.
  - **Android Runtime (ART):** For Android versions beyond 5.0, apps have their own runtime processes and instances. Android runtime has features such as ahead-of-time (AOT) compilation, just-in-time (JIT) compilation, optimized garbage collection (GC), and Dalvik Executable format (DEX) files to compress machine code.
  - **Core Libraries:** The set of core libraries allows developers to write Android applications using Java.

- **Hardware Abstraction Layer** <br>
  The hardware abstraction layer is used to expose the device’s hardware capabilities to the Java API framework that resides at a higher level. It acts as an abstraction layer between the hardware and the software stack. HAL comprises various modules that are required for the hardware equipment in the device, such as audio, camera, Bluetooth, sensors, and so on.

- **Linux Kernel** <br>
  The Android OS relies on the Linux kernel. This layer comprises low-level device drivers such as audio driver, binder (IPC) driver, display driver, keypad driver, Bluetooth driver, camera driver, shared memory driver, USB driver, Wi-Fi driver, Flash memory driver, and power management for the various hardware components. The functions of this layer include memory management, power management, security management, and networking.

---
## Android Device Administration API 
The Android Device Administration API allows developers to build apps that enforce security policies on devices. These apps are often used in enterprises to give IT teams control over employee devices, such as enforcing password rules, restricting features, or managing data. This helps organizations maintain security across all Android devices used in the workplace.

Some examples of the types of applications that might use the device administration API are as follows:
- Email clients
- Security applications that perform a remote wipe
- Device management services and applications

The table below lists the policies supported by the Android device administration API: 
| Policy                                  | Description |
|-----------------------------------------|-------------|
| Password enabled                        | Requires that devices ask for a PIN or password |
| Minimum password length                 | Set the required number of characters for the password. For example, you can require a PIN or password to have at least six characters. |
| Alphanumeric password required          | Requires the password to have a combination of letters and numbers and may include symbolic characters. |
| Complex password required               | Requires the password to contain at least a letter, a numerical digit, and a special symbol. Introduced in Android 3.0. |
| Minimum letters required in password    | The minimum number of letters required in the password for all admins or a particular one. Introduced in Android 3.0. |
| Minimum lowercase letters required in password | The minimum number of lowercase letters required in the password for all admins or a particular one. Introduced in Android 3.0. |
| Minimum non-letter characters required in password | The minimum number of nonletter characters required in the password for all admins or a particular one. Introduced in Android 3.0. |
| Minimum numerical digits required in password | The minimum number of numerical digits required in the password for all admins or a particular one. Introduced in Android 3.0. |
| Minimum symbols required in password    | The minimum number of symbols required in the password for all admins or a particular one. Introduced in Android 3.0. |
| Minimum uppercase letters required in password | The minimum number of uppercase letters required in the password for all admins or a particular one. Introduced in Android 3.0. |
| Password expiration timeout             | When the password will expire, expressed as a delta in milliseconds from when a device admin sets the expiration timeout. Introduced in Android 3.0. |
| Password history restriction            | This policy prevents users from reusing the last n unique passwords. Typically, you can use this policy in conjunction with `setPasswordExpirationTimeout()`, which forces users to update their passwords after a specified amount of time has elapsed. Introduced in Android 3.0. |
| Maximum failed password attempts        | Specifies how many times a user can enter the wrong password before the device wipes its data. The Device Administration API also allows administrators to remotely reset the device to factory defaults. This secures data in case the device is lost or stolen. |
| Maximum inactivity time lock            | Sets the length of time since the user last touched the screen or pressed a button before the device locks the screen. When this happens, users need to enter their PIN or password again before they can access their devices and data. The value can be between 1 and 60 minutes. |
| Require storage encryption              | Specifies the encryption of storage, if the device supports it. Introduced in Android 3.0. |
| Disable camera                          | Specifies the camera-disabling feature. Note that this does not have to be permanent. The camera can be enabled/disabled dynamically based on context, time, and so on. Introduced in Android 4.0. |

In addition to supporting the policies mentioned above, the device administration API lets you perform the following:
- Prompt user to set a new password
- Lock device immediately
- Wipe the device’s data (i.e., restore the device to its factory defaults)

An example of an Android device administrator page is shown below: 

<p align="center">
  <img width="308" height="377" alt="image" src="https://github.com/user-attachments/assets/16fc874d-3da1-457e-a8f7-bec286ecec57" />
</p>

---
## Android Rooting
Android rooting is the process of gaining privileged “root access” to bypass restrictions set by manufacturers or carriers. It allows users to modify system settings, remove pre-installed apps, install custom operating systems, and run apps that need admin rights. Rooting is done by exploiting firmware vulnerabilities, placing the `su` binary in the system path (e.g., `/system/xbin/su`), and making it executable, giving full control over the device.

Rooting enables all the user-installed applications to run privileged commands such as
- Modifying or deleting system files, modules, ROMs (stock firmware), and kernels
- Removing carrier-or manufacturer-installed applications (bloatware)
- Low-level access to hardware that is typically unavailable to devices in their default configuration
- Improved performance
- Wi-Fi and Bluetooth tethering
- Installing applications on SD card
- Better user interface and keyboard

Rooting also comes with many security risks and other risks to your device, including:
- Voiding your phone's warranty
- Poor performance
- Malware infection
- “Bricking” the device

One can use tools such as One Click Root, KingoRoot, and so on to root Android devices. 

---
## Rooting Android Using KingoRoot 
🔗Source: [https://www.kingoapp.com] <br>
KingoRoot is a tool used to root Android devices. It can be used with or without a PC. KingoRoot helps users root their Android devices to achieve the following:
- Preserve battery life
- Access root-only apps
- Remove carrier “bloatware”
- Customize appearance
- Attain admin level permission

The following steps are involved in rooting an Android device with this tool: 

### Android Rooting With PC
- Download KingoRoot Android (PC Version) and install it on your desktop.
- Run the tool and connect the device to the computer with a USB cable.
- Enable the USB debugging mode on your Android device.
- Now, the tool will install the latest drivers on your PC.
- You will see a new screen on your desktop with your device name and the “ROOT” button.
- Click on ROOT to root your device.

### Android Rooting Without PC
- Enable installation from unknown sources in your Android device.
- Download KingoRoot.apk on your Android device from Play Store.
- Install and launch KingoRoot.
- Press “One Click Root” on the main interface of the app.
- Wait for a few seconds until the root result appears on the display.
- Attempt multiple times in case of failed rooting or you can try the PC version.

<p align="center">
  <img width="454" height="399" alt="image" src="https://github.com/user-attachments/assets/56014939-3298-425a-838a-91cebc197936" />
</p>

---
## Android Rooting Tools
- **One Click Root** [https://oneclickroot.com] <br>
  One Click Root is an Android rooting software that supports most devices. It comes with extra fail-safes (such as instant unrooting) and offers full technical support. It allows the rooting of an Android smartphone or tablet and provides access to additional features such as gaining access to more apps, installing apps on SD cards, preserving battery life, Wi-Fi and Bluetooth tethering, installing custom ROMs, and accessing blocked features. <br>
  Following are the steps to root an Android device:
  - Download One Click Root (PC Version) and install it on your desktop
  - Connect the device to the computer with a USB cable
  - Enable USB debugging mode on the Android device
  - Run the One Click Root tool on a PC and click on ROOT to root the device

  <p align="center">
    <img width="557" height="407" alt="image" src="https://github.com/user-attachments/assets/af1cd8f6-9c53-4b49-90dd-aa827bb2cdf6" />
  </p>

Some additional Android rooting tools are as follows:
- **TunesGo** [https://tunesgo.wondershare.com]
- **RootMaster** [https://root-master.com]
- **Magisk Manager** [https://magiskmanager.com]
- **KingRoot** [https://kingrootapp.net]
- **iRoot** [https://iroot-download.com]
