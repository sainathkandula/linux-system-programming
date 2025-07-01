# Computer Booting Process – Step-by-Step Explanation

When you press the power button on a computer or mobile device, a series of steps are triggered to load the operating system (OS). This process is known as booting. Below is a detailed breakdown of what happens during booting:
```

## Step 1: Power Supply Turns On  
- The Power Supply Unit (PSU) activates.  
- Electricity flows to all key components: CPU, RAM, motherboard, storage, etc.  
- The CPU receives power but cannot start immediately because it has no instructions in RAM yet.


## 🧠 Step 2: Boot ROM / BIOS Runs (Startup Program)  
- The CPU looks for the first instructions to execute.  
- These instructions are stored in a special non-volatile memory called:  
  - BIOS (Basic Input/Output System) in older systems.  
  - Boot ROM in embedded or mobile systems.  

**Purpose of Boot ROM/BIOS:**  
- It performs a Power-On Self Test (POST):  
  - Checks if RAM, CPU, keyboard, display, etc. are working.  
  - Initializes hardware components.  
- It is not stored in RAM, but in ROM, because RAM is empty and volatile at startup.
```

## 💽 Step 3: Locating Bootable Storage  
- After POST, BIOS/Boot ROM looks for a bootable storage device like:  
  - Hard Disk (HDD)  
  - Solid State Drive (SSD)  
  - eMMC (in phones or embedded devices)  
  - USB drives or SD cards
    ```

## 📂 Step 4: Loading the Bootloader  
- The system reads the first tiny part of the selected storage.  
- This part is called the MBR (Master Boot Record).
  ```

**What is the MBR?**  
- MBR is a small block (first 512 bytes) at the start of the disk.  
- It contains:  
  - A tiny program (bootloader stage 1).  
  - A partition table (map of the disk).  

**What Happens Next?**  
- The tiny bootloader code in the MBR is copied into RAM.  
- CPU begins executing this code from RAM.  
- This code knows how to find and load the full bootloader or OS kernel.
  
## 🧾 Step 5: Bootloader Loads the Operating System  
- The full bootloader (e.g., GRUB, U-Boot, Android Bootloader) takes over.  
- It loads the operating system (like Windows, Linux, Android) from disk into RAM.
  ```

## 🖥️ Step 6: Operating System Starts  
- The OS initializes drivers, user interface, and background services.  
- The login screen, desktop, or home screen appears.
  ```

## ✅ System Ready  
- The system is now ready for user input.  
- You can now use applications, access files, and work normally.
  ```


# 🧠 Summary of Booting Steps

| Step              | Description                                               |
|-------------------|-----------------------------------------------------------|
| 1. Power On       | Electricity powers up CPU, RAM, motherboard               |
| 2. Boot ROM Runs  | CPU executes ROM code; POST runs to test hardware         |
| 3. Find Boot Device | BIOS scans for a bootable disk (SSD, eMMC, etc.)        |
| 4. Load MBR       | MBR (first tiny part of storage) is copied to RAM         |
| 5. Load Bootloader| Bootloader finds and loads the OS into RAM                |
| 6. Start OS       | Operating system initializes and shows interface          |
| ✅ System Ready   | User can start using the system                           |
```

