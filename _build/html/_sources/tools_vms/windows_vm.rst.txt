.. _windows_vm:


Lab Test VM
***********

LAB Test VM Prep:
-----------------

#. Upload Windows2012R.qcow2 image from under link 
	     - **BLR:** \nfs://10.136.239.13/workshop_staging/Windows2012R2.qcow2
	     - **PHX:** \nfs://10.42.194.11/workshop_staging/Windows2012R2.qcow2
	     - **RTP:** \nfs://10.55.251.38/workshop_staging/Windows2012R2.qcow2

#. Create VM
#. Click “+Add New Disk” under Disks locate to "Windows2012R2.qcow2"
#. Choose Primary for “Network”
#. Power on the Windows2012 VM
#. Launch Console and configure windows 2012
#. Login and verify it is on the network Install NGT: Click the Windows 2012 VM and choose “Manage Guest Tools” Select all options and click “Submit”
#. From the Windows Conlose, browse to the CDROM drive and run the installation with all defaults
#. Eject CDROM
#. May two clones of this system to have more test systems **make sure CDROM is ejected**
