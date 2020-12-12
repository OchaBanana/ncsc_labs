.. _3a_manually_importing:


Lab 3a: Manually import VMs (Optional)
**************************************

Manually importing ESXi VMs to AHV
----------------------------------

This lab is important as you may need to import a Virtual Disk manually. The steps are generally the same to import vDisks into Nutanix AHV. I suggest this as optional because tools like Move will be used in most cases.

Preparing
---------

A Prepare the VM on the ESXi host was installed with Nutanix VirtIO drivers.

#. Add the source hypervisor host IP address to the target AHV cluster Filesystem Whitelist.
#. You can use Storage vMotion for the VM disks to Nutanix AHV container datastore.

Converting
----------

Converting the migrated Disks to AHV format

#. In the Prism UI, click Settings > Image Configuration.
#. In the Image Configuration Dialog Box, click Upload the Image
#. In the Create Image dialog box, complete the indicated fields.
#. Log in to the Prism UI using your Nutanix credentials.
#. At the top left corner, click Home > VM. The VM page appears.
#. Click + Create VM in the corner of the page.
#. CLONE FROM IMAGE SERVICE: Click the drop-down menu and choose the image you created previously.
#. Power on VM