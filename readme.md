PXE OS Deploy
=============

Dependencies
------------

The flavor of depencies do not matter, all DHCP servers have the options needed, 
all the HTTP servers can make a directory listening and so on.
If I change from the DHCP server flavor, I am gonna put the files here.
In my LAB I am using:

* DHCP Server (Cisco SMB SF300)
* TFTP Server (tftpd-hpa)
* NFS Server (Seagate BlackArmor 220)
* HTTP Server (Seagate BlackArmor 220)

Usage
-----

1. Set TFTP server with pxelinux.cfg/default, pxelinux.0 and .32 menus 
(from syslinux package), the Kernel and Initdr file (from .iso).
2. Set DHCP server options next-server for the TFTP IP address and
filename (or bootfilename) for the pxelinux.0 file.
3. Set the NFS server for exporting the images (CentOS case), can be
just read only.
4. Set the HTTP server for serving the KS/Seed files and files for
Ubuntu 14-04 mirror.

Ubuntu 14.04 Server
-------------------

* Seed file
* Using local mirror (mounted .iso file) via HTTP
* Kernel and Initrd from netboot folder

CentOS 7.0 Minimum
------------------

* Kickstart File
* Using local mirror (mounted .iso file) over NFS

TODO
----

* Ubuntu fetching some packages from security.ubuntu.com (try
to find a way to get this files from local mirror)
* Ubuntu sets hostname from DHCP (Cisco provides this in IP format)
hardcode hostname after installation 
