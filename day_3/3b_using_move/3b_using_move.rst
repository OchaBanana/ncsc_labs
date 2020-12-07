.. _3b_using_move:


Lab 3b: Nutanix Move
********************

Using Move VMs to migrate from ESXi to AHV
------------------------------------------

#. Under VMs Power on “MOVE VM” 
#. Choose “Launch Console” 
#. Login using User: admin Password: Nutanix/4u 
#. Choose no to keep DHCP IP 
#. Under VMs in Prism you should see the IPs assigned to Move 
#. Open a internet browse to http://<Move_IP> 
#. Reset password and then login 
#. Choose a Source Environment 
     - a. Add Source ESXi Fill in the needed information provided by instructor and click “Add” 
     - b. Add a Target Fill in your cluster information and click “Add” 
     - c. Create a Migration Plan 
     - d. Have the VM start immediately and cut it over when