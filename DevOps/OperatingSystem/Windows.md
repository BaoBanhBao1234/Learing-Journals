1. What is Windows?
- Windows is an operating system developed by Microsoft. An operating system manages computer hardware and provides services that applications use to run.
- Windows provides a graphical desktop environment, built-in system tools, and support for a wide range of software and devices.
- Windows is a product family that includes desktop editions, Windows Server, and Windows for specialized devices. The Microsoft Windows page currently highlights Windows 11 for personal computers.
- The Windows technical documentation covers application and hardware development, Windows client administration, Windows Server, and Windows for IoT.

2. What an Operating System Does
- Manages hardware resources such as the processor, memory, storage, and connected devices.
- Runs applications as processes and provides system services that applications can request.
- Organizes files and folders on storage volumes and controls access to them.
- Provides user accounts, permissions, networking, and a user interface for working with the computer.
- Windows includes both user-mode and kernel-mode components that work together to run applications and manage the system.

3. Windows Architecture: User Mode and Kernel Mode
- **User mode** is where most applications run. Windows gives each process its own virtual address space, which helps isolate it from other applications.
- **Kernel mode** is where core operating system components run and where the system can access hardware and protected resources.
- Applications request operating system services through system interfaces rather than directly accessing protected hardware and kernel memory.
- Many device drivers run in kernel mode, although some drivers can run in user mode.
- A failure in a user-mode application is generally isolated to that process. A serious kernel-mode or driver failure can affect the whole operating system.

4. Files, Folders, and Storage
- Windows organizes data using volumes, directories (folders), and files.
- A file system defines how files and folders are stored, named, and accessed on a volume.
- NTFS (New Technology File System) is the default file system for modern Windows-based operating systems.
+ NTFS supports file and folder permissions, encryption features, quotas, and recovery mechanisms.
+ Windows also supports other file systems for particular devices and use cases.
- Windows paths commonly use drive letters, such as `C:\Users\Name\Documents`.
- The Windows Registry stores configuration data and settings for Windows and applications. It is structured as keys and values; changes to it should be made carefully.

5. Applications, Processes, Services, and Drivers
- An **application** is a program used to perform a task, such as editing documents or browsing the web.
- When an application runs, Windows creates a **process** that contains the program's running state and resources.
- A **service** is a background component that can provide system or application functionality, sometimes without a user being signed in.
- A **device driver** allows Windows and applications to communicate with a particular type of hardware.
- Task Manager can be used to view running applications, processes, system performance, and startup applications.

6. User Accounts and Security
- Windows uses user accounts, groups, and permissions to control access to files, settings, and system resources.
- A standard user account has fewer privileges than an administrator account, which helps limit the effect of mistakes or malicious software.
- User Account Control (UAC) can ask for consent or administrator credentials when an operation requires elevated privileges, such as installing software or changing protected system settings.
- Windows security features and supported hardware vary by edition, version, device, and configuration.
- Keep Windows and applications updated, use strong sign-in protection, and install software from trusted sources.

7. Ways to Use and Manage Windows
- The graphical user interface (GUI) includes the desktop, Start menu, taskbar, File Explorer, and settings pages.
- **Command Prompt** runs Windows commands in a text-based shell.
- **PowerShell** is a command-line shell and scripting environment used for administration and automation.
- Many system commands can be run without administrator rights; commands that change system-wide settings may require an elevated terminal.
- Windows Update delivers operating system updates and security fixes. Organizations can also use management tools and policies to configure Windows devices.

8. Useful Windows Commands
- Open Command Prompt by searching for `cmd` in the Start menu. Use **Run as administrator** only when the task needs elevated permissions.
+ `winver`: display Windows version information.
+ `systeminfo`: display detailed system and operating system information.
+ `ipconfig`: show network adapter IP configuration.
+ `ipconfig /all`: show detailed network configuration, including DNS and physical addresses.
+ `ipconfig /displaydns`: display the local DNS resolver cache.
+ `ipconfig /flushdns`: clear the local DNS resolver cache.
+ `nslookup example.com`: query DNS for a hostname.
+ `getmac /v`: display MAC addresses and adapter details.
+ `powercfg /batteryreport`: create a report about battery usage on supported devices.
+ `tasklist`: display running processes.
+ `dir`: list files and folders in the current directory.
+ `cd`: display or change the current directory.
+ `cls`: clear the Command Prompt screen.
- Commands and options can vary by Windows version and environment. Use `command /?` to view help for a command.

9. Key Takeaways
- Windows is an operating system that manages hardware and provides a platform for applications.
- Windows separates most applications into user-mode processes and uses kernel-mode components to manage core system functions.
- NTFS is the default file system on modern Windows systems and supports permissions and other storage features.
- User accounts, permissions, UAC, and updates are important parts of Windows security and administration.
- The GUI, Command Prompt, and PowerShell provide different ways to use and manage Windows.

10. Sources
- Microsoft Windows: Explore Windows https://www.microsoft.com/windows/
- Microsoft Learn: Windows Documentation https://learn.microsoft.com/en-us/windows/
- Microsoft Learn: Overview of Windows Components https://learn.microsoft.com/en-us/windows-hardware/drivers/kernel/overview-of-windows-components
- Microsoft Learn: User Mode and Kernel Mode https://learn.microsoft.com/en-us/windows-hardware/drivers/gettingstarted/user-mode-and-kernel-mode
- Microsoft Learn: NTFS overview https://learn.microsoft.com/en-us/windows-server/storage/file-server/ntfs-overview
- Microsoft Learn: User Account Control Overview https://learn.microsoft.com/en-us/windows-server/security/user-account-control/user-account-control-overview
- Microsoft Learn: ipconfig command https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/ipconfig
- NetworkChuck: 40 Windows Commands you NEED to know (YouTube) https://www.youtube.com/watch?v=Jfvg3CS1X3A
