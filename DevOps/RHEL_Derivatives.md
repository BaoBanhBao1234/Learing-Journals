1. What is RHEL?
- RHEL stands for Red Hat Enterprise Linux. It is a Linux distributions designed for enterprise workloads
- RHEL runs on physical servers, virtual machines and cloud infrastructure
2. Why do business use RHEL?
- RHEL provides a maintained platform with security updates, a defined lifecycle and enterprise support options
- A subscription provides access to software, update and services according to its terms
3. RHEL and Derivatives
- RHEL: enterprise Linux provided by Red Hat
- Rocky Linux: A community enterprise distribution targeting compatibility with RHEL
- Alma Linux: A community enterprise distribution targeting RHEL, ABI compatibility
- Fedora
- CentOS Stream is part of RHEL development. It is different from former CentOS Linux rebuild
4. Software Management
- RHEL uses RPM packages, DNF manages software installation, updgrades, removal adn dependencies
- dnf search nginx : search for a package
- dnf info nginx: Show package information
- sudo dnf install nginx: install nginx
- sudo dnf upgrade: upgrades installed packages
- sudo dnf remove nginx: remove nginx
- dnf repolist: list enabled repositories
5. Services adn logs
- RHEL uses systemd to manage system services. The "systemctl" command controls these services
- sudo systemctl start nginx: start the service now
- sudo systemctl stop nginx: stop the service
- sudo systemctl restart nginx: restart the service
- sudo systemctl enable nginx: enable startup at boot
- systemctl status nginx: check service status
- sudo journalctl: -u nginx: Read service logs
- Starting a service and enabling it at boot are separate actions
Ex: sudo systemctl enable --now nginx
-> If service dont run, check status and logs to find reason
6. SELinux
- SELinux stands for Security-Enhanced Linux. It applies security policies to control access to system resources
- Enforcing: Enforces policy and records denials
- Permissive: records policy violations without blocking them
- Disabled: SELinux is disabled
- getenforce: check status
7. Firewall
- A firewall controls network traffic. RHEL commonly uses firewalld to manage firewall rules