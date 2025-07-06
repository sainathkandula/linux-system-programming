### RISC vs CISC – Explanation

RISC (Reduced Instruction Set Computer) uses a small number of simple instructions that are fast and take only one clock cycle to execute. This makes the processor faster and more efficient, but it may need more instructions to complete a task.

CISC (Complex Instruction Set Computer) uses a large number of complex instructions, where one instruction can do multiple operations. This reduces the number of instructions per program but makes each instruction slower and the hardware more complex.


---

###  Key Difference (in one line)

 **RISC uses simple, fast instructions and is efficient; CISC uses complex instructions to do more with fewer lines but runs slower.**

---

### Difference Between Android Booting and Linux Booting

Android booting starts from Boot ROM inside the SoC, then loads bootloader, kernel, init, Zygote, System Server, and finally the Launcher (home screen). It is optimized for mobile devices and uses special processes like Zygote to launch apps faster.

Linux booting starts with BIOS or UEFI, then loads a bootloader like GRUB, followed by the kernel, init/systemd, login manager, and finally the desktop environment or command-line interface. It is designed for PCs and servers.


###  Q: What happens if the Zygote process fails to start?
**A:** The system cannot launch apps, and Android will fail to boot to the home screen.

### Q :What is Binder in Android?

**Binder** is Android’s **IPC (Inter-Process Communication)** mechanism.  
It allows different **apps**, **services**, or **system components** to communicate with each other **safely and efficiently**, even if they run in **separate processes**.

---

