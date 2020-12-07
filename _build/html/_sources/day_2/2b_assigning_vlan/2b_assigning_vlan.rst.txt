.. _2b_assigning_vlan:


Lab 2b: Networking: Assigning VLANs (Optional Lab)
**************************************************

Assigning VLANs for Host & CVM
------------------------------

This lab is important as you will need to change the VLANs when systems are in Trunked production networks this is the case with most production environments.

.. note:: It’s recommend connecting by remote console in IPMI because you may lose connection if you are SSH into the node


#. ssh into each of your **AHV** Hosts
#. Assign port br0 to the VLAN that you want the host be on.

   .. code-block:: bash
       
     ovs-vsctl set port br0 tag=<host_vlan_tag>

#. Confirm VLAN tagging on port br0.

   .. code-block:: bash
       
     ovs-vsctl list port br0

#. From host console Log on to the **Controller VM**.

   .. code-block:: bash
       
     ssh nutanix@192.168.5.254

#. Assign the public interface of the **Controller VM** to a VLAN.

   .. code-block:: bash
       
     change_cvm_vlan <vlan_id>

.. note::
    Hosts VLAN and CVM VLAN must be same.
