.. _2c_snapshot:


Lab 2c: Snapshot 
****************

Snapshot Local and Recover
--------------------------

Lab Setup
---------

This lab requires applications provisioned as part of the :ref:`windows_vm`.


Nutanix Data Protection
-----------------------

Purpose: Explore the rich set of integrated data protection and disaster recovery
Capabilities in the Nutanix solution

#. Log into Prism
#. Click on “+ Protection Domain” button > “Async DR”
#. Create a protection domain with a unique name by going through the wizard
     - a. Name the protection domain ex “PD-Prod-<*Initial*>”
     - b. Choose VMs to include in the protection domain
             - choose the cloned VM you created in the :ref:`windows_vm`
             - choose “Protect Selected Entities” click Next
     - c. Click “New Schedule” Setup a schedule for the protection domain
             - choose “**Repeat every “1” day**”
             - Create Schedule
             - **Close**
     - d. Simulate a few days of snapshots by selecting the **Async DR** you created in table view
             - Select “**Take Snapshot**” and hit save and repeat a few times.

   .. note:: You may modify the VM so that you can snapshot different version of your VM Under “**Local Snapshots**” for this Protection Domain you should see a few listed

#. Restore VM from Replication:
     - a. Select the Protection Domain containing the VM snapshot
     - b. Choose the Local Snapshot under “Local Snapshots” with the timestamp and click restore
     - c. Choose all VMs or just certain VMs you wish to restore
     - d. Create new entities:
             - Choose to create new entity to restore to a new VM. (Prefix: Nutanix-Clone-)
             - Look at VMs to see there are new VMs restore from your snapshots
     - e. Overwrite Existing Entities (remember to use a clone to have a copy of your VM):
             - Choose to overwrite your VM while online
             - The VM should boot into the VM at the point in time of the snapshot.
