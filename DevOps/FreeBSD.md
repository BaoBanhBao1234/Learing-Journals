1. What is FreeBSD?
- FreeBSD is a free, open-source, UNix - like operating system. It belongs to the BSD family and is not a Linux distribution
- BSD stands for Berkeley Software Distribution
2. What is FreeBSD used for?
- FreeBSD can be used on servers, desktop computers and embedded systems
3. Kernel and base sysrem
- The kernel manages resources such as CPU, memory, and devices
- FreeBSD develops its kernel and use system tools together as an integrated base system
4. Packages and ports
- Package is an application already compiled for installation
- Ports collection is Instructions and supporting files for building applications from source
- pkg is a tool for managing binary packages
- Packages save compilation time. Ports allow build-time customization
- pkg search nginx: search for packages
- pkg install nginx: install nginx
- pkg info: list installed packages
5. Services
- A service provides a function and often runs in the background
- FreeBSD manages services through its resystem. The "service" command controls services, "while /etc /rc.conf" contains many startup settings
Ex: sysrc nginx _enable = "YES": enable at boot
    service nginx start: start now
    service nginx status: check status
6. Important features
- Jails: isolated environments sharing the host kernel
- ZFS: a filesystem and volume manages with data-integrity and snapshot features
- bhyve: a hypervisor for running virtual machines
- A jail shares the host kernel. A virtual machine runs its own guest kernel