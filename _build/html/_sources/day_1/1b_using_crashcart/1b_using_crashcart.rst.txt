.. _1b_using_crashcart:


Lab 1b: crashcart network_configuration
***************************************

Using the crashcart network_configuration command
-------------------------------------------------

In a remote install or deployment the IPMI was set ahead of time for remote access this command will now be use to set the HOST and CVM IP as well as Network settings.


#. Continued from the previous console we can run the following command:
     - a. “*cp ~/firstboot/fc_progress.py ~/nutanix-network-crashcart/*” - This file is missing in the crashcart path and has been fixed in future releases 5.16.1+
     - b. “*cd /root/nutanix-network-crashcart/*” - change directory to crashcart folder
     - c. “*./network_configuration*” – opens up Nutanix Network Configuration
     
#. Note the network changes available to you on this local system:

    .. figure:: images/1_network_config.png

#. For this lab let’s choose “**Cancel**” as the IPs are already set.
#. You can now “**exit**” and close your remote console
