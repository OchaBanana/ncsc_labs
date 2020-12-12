.. _1b_using_crashcart:


Lab 1b: crashcart network_configuration
***************************************

Using the crashcart network_configuration command
-------------------------------------------------

In a remote install or deployment the IPMI was set ahead of time for remote access this command will now be use to set the HOST and CVM IP as well as Network settings.

#. Make sure your console at **AHV Host** 
   - ``root@<host_name>``
#. Continued from the previous console we can run the following command:
  - a. change directory to crashcart folder

      .. code-block:: bash

          cd /root/nutanix-network-crashcart/

  - b. opens up Nutanix Network Configuration

      .. code-block:: bash

          ./network_configuration   


  .. note:: If cannot run this command it's mean this file is missing in the crashcart path, but has been fixed in future releases 5.16.1+. You can copy the file following command:

      .. code-block:: bash
                 
          cp ~/firstboot/fc_progress.py ~/nutanix-network-crashcart/

#. Note the network changes available to you on this local system:

    .. figure:: images/1_network_config.png

#. For this lab let’s choose “**Cancel**” as the IPs are already set.
#. You can now “**exit**” and close your remote console
