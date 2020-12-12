.. _1e_install_foudation:


Lab 1e: Install Foundation VM (Optional Lab)
********************************************

Install Foundation VM on your Laptop 
------------------------------------

This is important lab to understand Baremetal unfortunately we run through these steps with our Remote Labs due to network accessibility. Use this lab as a reference lab. When you would need to baremetal or image a single node you will have to use Foundation VM or Portable Foundation.

Downloading the needed Foundation & AOS:
----------------------------------------

#. Open a web browser and log in to the `Nutanix Support portal: <https://portal.nutanix.com/page/downloads?product=foundation>`_
#. Download **Foundation VM**
#. You will also need to download an **AOS/AHV** bundle
#. Extract Tar (7 zip) and import **Foundation_VM-4.x.ovf** into VirtualBox
#. Launch VM verify networking is bridged (See also Appendix files for further assistance with Oracle Virtual Box and VMware Workstation)
#. Set the IP by clicking the set_foundation_ip_address Icon – use an IP within the CVM/Host network
#. Use your laptop internet browser to browse to the IP set in previous step – IP on Laptop from the IP table (NOTE: Alternately You could use the icon “Nutanix Foundation” on the VM desktop but will have lower resolution and not be able to upload file from the browser from your laptop)
#. Out of the Factory you would see the nodes in the Discovery pane under the “2. Nodes” section. If you are seeing discovered nodes you can skip the next step. However in our labs the blocks most likely were not left in an “out of factory” state and you will need to do the **BareMetal** steps below.
#. To start **BareMetal** steps, click “Reach more nodes by manually entering the **MAC Addresses**. You can get MAC from sticker on the back of each node. The other option to use the **IPMI IPs** can be used if you are able to set those before Foundation the server.

.. note::

    “**Software Only**” system will come with nothing pre-installed you must to use these BareMetal steps. In the same fashion you can not auto-discover any of your nodes if it is part of a cluster.
