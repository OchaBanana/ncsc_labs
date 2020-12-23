.. _1c_foundation_cvm:


Lab 1c: Foundation from a CVM
*****************************

Foundation software is installed on each CVM when they are imaged out of the factory. In some case the hardware is sold “Software Only” which means software must be installed “Baremetal”. In this case for remote installs Foundation will need to be installed on a local system in order to image the nodes. Please see also Baremetal steps in Field Installation Guide.


#. Open a web browser to your CVM IP: `http://<CVM_IP:8000>` **USE YOUR ASSIGNED CVM IP**
#. Page 1. Start fill form with your `Assigned lab Network IP <https://docs.google.com/spreadsheets/d/1QmYpmG1lo_3bo3iYONy-uPzIQGvnm4lHf1lx8URXj7Y/edit?usp=sharing>`_ settings provided and hit “Next”
#. Page 2. Nodes notice your remaining nodes should detect. Because they are previously configured the IPs autofilled but normally out of factory they will require you put your `desired IPs <https://docs.google.com/spreadsheets/d/1QmYpmG1lo_3bo3iYONy-uPzIQGvnm4lHf1lx8URXj7Y/edit?usp=sharing>`_. **ONLY SELECT YOUR NODE IN THIS LAB**. We will be making a single node cluster. Give it a Host name of **HOST-**\<*initials*>.
#. Page 3. Cluster page, let’s choose to “Skip automatic cluster formation” and give it 24GB of memory and hit “Next”. Note only a select few models are supported in Single-node cluster in foundation we will use “Skip” and do this manually since we do not have any single node models in the labs.
#. Page 4. AOS we will keep the default factory imaged software “we will skip AOS installation” and hit “Next”
#. Page 5. Hypervisor same as previous step we will skip reimaging and hit “Next”
#. Page 6. IPMI only on baremetal installation you would you need this step. When using the factory image we can skip this and hit “Start”
#. Explore Logs to see live scripts running from Foundation. Estimated time 1-5 minutes to complete
#. We will now bring up your node as a single node cluster. Login to CVM again via SSH and run command :

     .. code-block:: bash

        cluster -s <cvm_ip> --cluster_function_list=one_node_cluster create

#. When completed. Open a web browser to IP: `http://<CVM_IP>` . Use admin with the Prism UI password “Nutanix/4u” provided in the lab. (You may change the password to one you’d like to use) *Recommended to use Labs Password* **nx2TechXXX!**

Setting up cluster
------------------

Please following `Assigned lab Network IP <https://docs.google.com/spreadsheets/d/1QmYpmG1lo_3bo3iYONy-uPzIQGvnm4lHf1lx8URXj7Y/edit?usp=sharing>`_

#. Cluster Info: Click at **"Unnamed"** cluster name beside **X** icon at top-left.
   - Cluster name: Your assigned cluster-name or disign by yourself
   - Cluster IP: Your assigned IP (*CVM_IP + 1*)

#. Add DNS: To **Home** menu > **Settings** > Name Servers
   - fill 10.42.194.10 then click **+Add**

#. Add NTP: To NTP Servers
   - fill 0.pool.ntp.org then click **+Add**

Add Network
-----------

Pease following `Assigned lab Network IP <https://docs.google.com/spreadsheets/d/1QmYpmG1lo_3bo3iYONy-uPzIQGvnm4lHf1lx8URXj7Y/edit?usp=sharing>`_
l
#. **Network Config**
#. **+ Create Network**
	- **Network Name:** Primary-<*Initial*>
	- **VLAN ID:** 0
	- Select **Enable IP address management**
	- **Network IP Address / Prefix Length:** *10.xx.xx.0/25*
	- **Gateway IP Address:** 10.xx.xx.1
	- **DNS:** 10.42.194.10
	- Laeve blank for Domain Search, Domain Name, TFTP Server Name, Boot File Name
	- ** + Create Pool**
	   - **Start Address:** Your assigned IP
	   - **End Address:** Your assigned IP 

#. **Save**