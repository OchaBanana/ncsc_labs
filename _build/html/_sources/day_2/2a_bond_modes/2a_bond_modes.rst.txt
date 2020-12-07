.. _2a_bond_modes:


Lab 2a: Networking: Bond Modes in AHV
*************************************

In this lab we want to show you what it takes to set your bonds from the default **active-backup** to **balance-slb** (active/passive to active/active)

.. figure:: images/1_change_bond.png

Changing bond mode from Active/backup to balance-slb
-----------------------------------------------

#. ssh into one of your CVMs
#. To show the bond mode of the host run the following command:

  .. code-block:: bash

     ssh root@192.168.5.1 "ovs-appctl bond/show br0-up"

**Notice** the bond_mode should default to **active-backup**

#. Change the bond mode to balance-slb run the following command:

  .. code-block:: bash

     ssh root@192.168.5.1 "ovs-vsctl set port br0-up bond_mode=balance-slb"

#. Set the recommended rebalance-interval to 30 sec with the following command:

  .. code-block:: bash

     ssh root@192.168.5.1 "ovs-vsctl set port br0-up other_config:bond-rebalance-interval=30000"

#. Verify the proper bond mode again:

  .. code-block:: bash

     ssh root@192.168.5.1 "ovs-appctl bond/show br0-up"

**Notice** the next rebalance should be less than **30000ms** bond_mode should be **balance-slb**

#. Repeat steps 1-5 for the remaining CVMs in order to change all ports modes to balance-slb
