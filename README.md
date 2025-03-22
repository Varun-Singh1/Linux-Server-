# Linux-Server-
Configuration of Linux Server
# DHCP Server Configuration: 
This document provides step-by-step guide for DHCP Server Configuration 
# 1. Check Availability of Repositories: 
List all available repos to ensure DHCP Server package is available or not. 
- ```bash
  yum repolist all
# 2. Verify if DHCP Package is installed or not:
check it by rpm and grep command.
- ```bash
  rpm -qa | grep dhcp
# 3. Install DHCP Server: 
Install DHCP Server package
- ```bash
  yum install dhcp-server.*86_64
# 4. Verify Installation: 
Check if DHCP Server packages are installed or not.
- ```bash
  rpm -qa | grep dhcp
  rpm -qa | grep dhcp-server
# 5. Detailed Information about DHCP Server: 
Display Detailled information about the installed DHCP Server packages.
- ```bash
  rpm -qi | grep dhcp-server
# 6. List documentation files of DHCP Server: 
List the documentation files included with DHCP Server. 
- ```bash
  rpm -qd | grep dhcp-server
# 7. List configuration files for DHCP Server: 
List the configuration files included for DHCP Server. 
- ```bash
  rpm -qc | grep dhcp-server
# 8. List all files installed in DHCP Server Packages: 
List all the files included with DHCP Server in its packages. 
- ```bash
  rpm -ql | grep dhcp-server
# 9. Example of Configuration File: 
display the example configuration file for dhcp configuration.
- ```bash
  vim /user/share/doc/dhcp-server/dhcpd.conf.example
  cat /user/share/doc/dhcp-server/dhcpd.conf.example | less
# 10. Edit the configuration file: 
Open the DHCP configuration file to edit it by reference from example file.
- ```bash
  vim /etc/dhcp/dhcpd.conf
# configuration will look like this 
- ```bash
   authoritative;
  subnet 192.168.31.0 netmask 255.255.255.0{
  range 192.168.31.32 192.168.31.246;
  option routers 192.168.31.1;
  option domain-name-servers 8.8.8.8, 8.8.4.4;
  option broadcast-address 192.168.31.255;
  default-lease-time 600;max-lease-time 7200;
  }

  
