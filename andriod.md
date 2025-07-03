#  What is Android?

**Android** is a mobile operating system mainly made by **Google**.  
It is used in many devices like:

- Smartphones  
- Tablets  
- Smartwatches  
- Smart TVs  
- Car displays  
- Even smart home appliances  

It is built on top of the **Linux kernel**, which helps control hardware like the CPU, memory, and other parts of a device.


##  Key Features of Android

### • Type: Operating System (OS)

Android is an **Operating System (OS)**.  
It manages all parts of the device:

- **Hardware** (like battery, screen, sensors)  
- **Software** (like apps and settings)  

It acts like a **bridge** between the hardware and the apps we use.


### • Based On: Linux Kernel

Android is built on the **Linux kernel**.  
Linux is a powerful, open-source system used in computers and servers.

Android also uses helpful open-source tools:

- `libc` – Helps Android talk to the system using the C programming language  
- `WebKit` – Used to show websites inside apps  


### • User Interface (UI)

Android’s design is made for **touch interaction**. You use your fingers to:

- Tap  
- Swipe  
- Scroll  

It also supports:

- 🎙 **Voice control** (like Google Assistant)  
-  **Hand gestures**  
- **Accessibility features** (like screen readers for visually impaired users)

##  Programming Languages Used in Android

Android apps and system parts are built using different languages:

### • Java

- First main language for Android development  
- Runs on **Android Runtime (ART)** or older **Dalvik VM**  
- Many Android APIs and features are built using Java

### • Kotlin

- Since 2017, **Kotlin** is the recommended language  
- Easier, safer, and more modern than Java  
- Can be used **together with Java** in the same project

### • C/C++

- Used for **fast and powerful** parts like games or audio processing  
- Developers use the **Android NDK** (Native Development Kit) to write in C/C++


##  Devices That Use Android

Android runs on many types of smart devices:

- **Smartphones** – Samsung, OnePlus, Vivo, Pixel  
- **Tablets** – Galaxy Tab, Lenovo Tab  
- **Smart TVs** – Android TV, Google TV  
- **Smartwatches** – Wear OS devices  
- **Car Displays** – Android Auto, Android Automotive OS  
- **Smart Devices** – Smart speakers, fridges, projectors, etc.


## Final Summary

Android is a **popular, powerful, and open-source** operating system.

  It is based on **Linux**  
  Supports many **programming languages**  
  Runs on **various smart devices**

Because of its flexibility and wide device support, Android is the **most used mobile OS in the world**.




---

## Andriod booting process
---

## ✅ 1. Boot ROM

- **Boot ROM** stands for **Boot Read-Only Memory**.
- It is the **first code** that runs when the device is powered on.
- It initializes minimal hardware like **RAM** and **clocks**.
- Then, it **loads the bootloader** from storage.

---

## ✅ 2. Bootloader

- A small program that prepares the device to load the kernel.
- **Two stages**:
  - **Primary Bootloader**: Sets up memory and basic hardware.
  - **Secondary Bootloader (U-Boot/Fastboot)**:
    - Loads the **kernel** and **device tree**.

### 📘 Simple Definitions:
- **Kernel**: The main part of Android that controls all hardware like screen, memory, and camera.
- **Device Tree (DTB)**: A file that tells Android what hardware is inside the device and how it is connected.

---

## ✅ 3. Kernel (Simplified)

- The **kernel** is the **main part of Android** that talks to the hardware.
- Based on the **Linux kernel**.
- Main responsibilities:
  - **Manages the CPU**
  - **Manages memory (RAM)**
  - **Controls hardware** (screen, camera, sensors)
  - **Loads the init program** from a temporary folder called `initramfs`

---

##  4. Init Process

- After the kernel finishes loading, it starts a program called **init**.
- This is the **first user-level program** in Android.
- It reads a script file called `init.rc`.

###  What Init Does:
1. **Mounts File Systems**:
   - `/system`: Stores Android OS files.
   - `/data`: Stores apps, settings, and personal data.
   - `/vendor`: Stores hardware support files.
2. **Sets Permissions**: Secures files and resources.
3. **Starts Zygote**: Prepares the system to launch apps quickly.

---

##  5. Zygote – Simplified

- Zygote is a **special process** started by init.
- It runs inside the **Android Runtime (ART)** or **Dalvik Virtual Machine (DVM)**.
- ART or Dalvik is used to run Android apps written in **Java** or **Kotlin**.

### 🛠️ What Zygote Does:

- Creates new app processes using `fork()` only when needed.
- Helps apps launch **faster**, even if reopened after closing.
- Common system libraries and UI parts are **preloaded**, so apps don't start from scratch.

###  Without Zygote:
If Android didn't use Zygote:
- It would have to:
  -  Start a new JVM every time
  -  Load system libraries and UI
  -  Re-initialize everything
- Result: **Slower app launches**

---

##  6. System Server

- Launched by Zygote.
- It’s the **main controller** of Android.
- Starts and manages all **core Android services** that apps depend on.

---

##  What Are System Services?

System services are **background helpers** that perform critical tasks like:

- Managing apps (start/stop/switch)
- Displaying app UI
- Handling battery, Wi-Fi, GPS, audio
- Sharing location with apps
- Managing volume, screen, etc.

---

##  Examples of Common Android System Services

|  Service           |   What it does                |    Example                         |
|--------------------|-------------------------------|------------------------------------|
| Activity Manager   | Starts or closes apps         | Opening WhatsApp                   |
| Window Manager     | Controls what appears on screen| Showing a full-screen video        |
| Power Manager      | Manages screen and battery    | Screen turns off when idle         |
| Package Manager    | Installs and updates apps     | Installing from Play Store         |
| Location Manager   | Shares GPS with apps          | Google Maps tracking location      |
| Audio Manager      | Controls volume and audio     | Changing sound with volume keys    |

---

##  Summary Table of Android Boot Components

| Stage         | Component       | Description                          |
|---------------|------------------|--------------------------------------|
| Boot ROM      | Boot Code        | Starts device and loads bootloader   |
| Bootloader    | U-Boot/Fastboot  | Loads kernel and device tree         |
| Kernel        | Linux Kernel     | Controls hardware and starts init    |
| Init          | `init.rc`        | Mounts filesystems and starts Zygote |
| Zygote        | JVM Process      | Prepares app processes               |
| System Server | Android Services | Starts system managers (services)    |
| Launcher      | Home Screen      | Main interface for the user          |

---


## Linux Booting Process

##  1. BIOS / UEFI

- BIOS (Basic Input/Output System) or UEFI is the **first code** that runs when the computer is powered on.
- It is **built into the motherboard** by the manufacturer.
- Checks basic hardware (like RAM, CPU, keyboard).
- Then it **finds and loads the bootloader** from a storage device (like HDD or SSD).

>  **Think of BIOS as the gatekeeper that starts the whole system.**

---

## 2. Bootloader (GRUB or LILO)

- The **bootloader** is a small program that loads the **Linux kernel** into memory.
- Common bootloaders: **GRUB** (most popular).
- It may offer a menu to choose different OS versions (e.g., Ubuntu, Windows).

---

##  3. Kernel

- The **Linux kernel** is the **core of the operating system**.
- It gets loaded into memory by the bootloader.
- The kernel:
  - Manages the **CPU, memory, devices, and file system**.
  - Mounts the **root filesystem `/`**.
  - Starts the **init process** (or systemd).

> **The kernel is like the engine of a car — it powers the whole system.**

---

##  4. Init Process (or systemd)

- This is the **first user-space program**, with process ID 1 (**PID 1**).
- Older systems used `init`; modern systems use **systemd**.
- It starts all the necessary **services and background processes**.

###  Examples of services started:
- **networking** – to connect to internet
- **login manager** – to allow user login
- **cron** – for scheduled tasks

>  **Think of it as the manager that opens all departments after the building is powered.**

---

## 5. Login Manager

- After services are started, the system shows a **login screen or console prompt**.
- The user enters their **username and password**.
- Once authenticated, the system loads the **user session**.

>  **It’s like checking in at a hotel — you provide credentials before accessing your room.**

---

## 6. Desktop Environment

- If it’s a desktop system, it shows a **graphical interface** (like **GNOME** or **KDE**).

---

##  Summary Table of Linux Boot Components

| Stage         | Component          | Description                                |
|---------------|--------------------|--------------------------------------------|
| BIOS/UEFI     | Firmware           | Hardware check and load bootloader         |
| Bootloader    | GRUB, LILO         | Loads the Linux kernel                     |
| Kernel        | Linux Kernel       | Initializes hardware and mounts filesystem |
| Init/Systemd  | PID 1 Process      | Starts services and daemons                |
| Login Manager | getty/gdm/lightdm | Authenticates user login                   |
| User Interface| GNOME/KDE/CLI      | Final interface for user interaction       |

---



