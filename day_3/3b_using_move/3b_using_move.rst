.. _3b_using_move:


Lab 3b: Nutanix Move
********************

Using Move VMs to migrate from ESXi to AHV
------------------------------------------

#. uplaod **Move** image using url: *nfs://10.42.194.11/workshop_staging/move-3.6.0.qcow2*
#. Create Move VM
    - **vCPU:** 2
    - **Core:** 2
    - **Memory:** 4
    - **Network:** Primary
#. Under VMs Power on “MOVE VM” 
#. Under VMs in Prism you should see the IPs assigned to Move 
#. Open a internet browse to http://<Move_IP> 
#. Reset password and then login 
#. Choose a Source Environment 
    - a. Click **+ Add Environment** to add Source ESXi Fill in the needed information provided by instructor and click “Add” 
    - b. Click **+ Add Environment** to add add a Target Fill in your cluster information and click “Add” 
    - c. Create a Migration Plan 
    - d. Have the VM start immediately and cut it over when