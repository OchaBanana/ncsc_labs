.. _2d_ssr:


Lab 2d: Self Service Restore SSR
********************************

.. note::
   - The Nutanix administrator can enable this feature for a VM through web interface or nCLI and in-guest actions can be performed by using NGT.
   - Only Async-DR workflow (1 hour or greater) is supported for the self-service restore feature.


#. Console to your created **Windows-VM**
#. Launch SSR Icon from the desktop
#. Login with your local administrator account
#. Notice you should see all snapshots available to you for that VM
#. Select a snapshot and choose to mount it as a drive letter.
#. Windows File Explorer should see the snapshot as a local drive.
#. Unmount and exit

.. note:: If the guest VM administrator fails to detach the disk, it gets automatically detached from the VM after 24 hours.
