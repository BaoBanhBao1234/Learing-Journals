1. What is RHEL?
- **RHEL** stands for Red Hat Enterprise Linux. It is a Linux distribution developed and supported by Red Hat for enterprise workloads.
- RHEL combines the Linux kernel with system utilities, libraries, applications, and administration tools as a maintained operating system platform.
- It can run on physical servers, virtual machines, public and private clouds, workstations, and edge systems.
- Red Hat provides defined lifecycle phases, security updates, product documentation, and support options for RHEL subscriptions. The exact services depend on the subscription and product lifecycle.

2. Why Organizations Use RHEL
- RHEL is designed to provide a consistent operating environment across different hardware and deployment locations.
- Organizations can use it to host applications and services, including in data centers, cloud environments, and edge deployments.
- Red Hat publishes documentation, security information, and lifecycle details for supported RHEL versions.
- A subscription can provide access to supported content, updates, and support services under its terms; it is separate from the open-source licensing of the software.

3. RHEL, Fedora, CentOS Stream, and RHEL-Compatible Distributions
- **Fedora** is a community Linux distribution and an upstream source for technologies that may later appear in enterprise products.
- **CentOS Stream** is a continuously delivered distribution that tracks just ahead of a corresponding RHEL minor release. It is part of the RHEL development process.
- **RHEL** is Red Hat's enterprise product with its own support and lifecycle model.
- **Rocky Linux** and **AlmaLinux** are independently governed community distributions that aim for compatibility with RHEL. They have their own release processes and support arrangements.
- CentOS Stream is different from the former CentOS Linux rebuild, which followed released RHEL sources.
- Similarity or compatibility does not mean that two distributions are identical or share the same vendor support, lifecycle, or guarantees.

4. Software and Package Management
- RHEL uses the **RPM** package format for software packages.
- **DNF** is the package manager used to search repositories, install and remove packages, update software, and resolve dependencies.
- The `rpm` command can query or manage individual package files, while DNF works with configured repositories and dependency information.
- Common DNF commands:
+ `dnf search nginx`: search enabled repositories for a package.
+ `dnf info nginx`: display package information.
+ `sudo dnf install nginx`: install a package and its dependencies.
+ `sudo dnf upgrade`: update installed packages.
+ `sudo dnf remove nginx`: remove a package.
+ `dnf repolist`: list enabled repositories.
- Review package changes before confirming them, especially on production systems.

5. Services and Logs
- RHEL uses **systemd** to manage system services and other system resources.
- `systemctl` can start, stop, restart, enable, and inspect services.
+ `sudo systemctl start nginx`: start a service now.
+ `sudo systemctl stop nginx`: stop a service.
+ `sudo systemctl restart nginx`: restart a service.
+ `sudo systemctl enable nginx`: configure a service to start at boot.
+ `sudo systemctl enable --now nginx`: enable a service at boot and start it now.
+ `systemctl status nginx`: view the service's current status.
- Starting a service and enabling it at boot are separate actions.
- `journalctl -u nginx` displays logs for a service. Check both service status and logs when troubleshooting.

6. SELinux and Security
- **SELinux (Security-Enhanced Linux)** applies mandatory access-control policies that limit how processes can access files, services, and other system resources.
- Common SELinux modes:
+ **Enforcing**: applies policy and records denials.
+ **Permissive**: does not block policy violations, but records them.
+ **Disabled**: SELinux policy is not active.
- `getenforce` displays the current SELinux mode.
- RHEL also provides security updates, security policies, and tools for managing system security. Security configuration should follow the requirements for the specific system and workload.

7. Firewall and Networking
- A firewall controls network traffic according to configured rules.
- RHEL commonly uses **firewalld** to manage firewall settings and zones.
- `firewall-cmd --state` checks whether firewalld is running.
- `firewall-cmd --list-all` displays the active zone's settings.
- Only allow the network services and ports required by the workload.

8. Useful Linux Command-Line Basics
- The shell reads commands and starts programs. IBM's Linux 101 learning path covers foundational Linux administration topics and command-line skills.
+ `pwd`: display the current directory.
+ `ls -l`: list files and directories with details.
+ `cd path`: change the current directory.
+ `mkdir name`: create a directory.
+ `cp source destination`: copy files or directories.
+ `mv source destination`: move or rename files or directories.
+ `rm file`: remove a file. Check the path and options carefully before removing data.
+ `less file`: read a text file a screen at a time.
+ `grep pattern file`: search a file for matching text.
+ `find path -name pattern`: search for files by name.
+ `df -h`: display filesystem space usage.
+ `du -sh path`: estimate the space used by a directory.
+ `free -h`: display memory usage.
+ `ps` and `top`: inspect running processes.
- Use `man command` or `command --help` to read documentation for a command.

9. Key Takeaways
- RHEL is Red Hat's enterprise Linux distribution, with supported releases, lifecycle information, and subscription-based services.
- Fedora, CentOS Stream, RHEL, Rocky Linux, and AlmaLinux are related but distinct projects with different roles and support models.
- RHEL uses RPM packages and DNF for repository-based software management.
- `systemd`, `systemctl`, and `journalctl` are central to service management and troubleshooting.
- SELinux and firewalld are important parts of RHEL security and network configuration.
- Linux command-line knowledge transfers across distributions, but package tools and some system defaults differ.

10. Sources
- Red Hat: Red Hat Enterprise Linux https://www.redhat.com/en/technologies/linux-platforms/enterprise-linux
- Red Hat: Red Hat Enterprise Linux documentation https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/
- Red Hat Documentation: Managing software with the DNF tool https://docs.redhat.com/en/documentation/red_hat_enterprise_linux/10/html-single/managing_software_with_the_dnf_tool/index
- IBM Developer: Learn Linux 101 https://developer.ibm.com/series/learn-linux-101/
- YouTube video supplied with the request https://www.youtube.com/watch?v=HEBvdSI0wGQ 
