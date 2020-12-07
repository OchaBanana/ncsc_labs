.. _2b_assigning_vlan:


Lab 2b: Networking: Assigning VLANs for Host & CVM (Optional reference Lab)
***************************************************************************

This lab is important as you will need to change the VLANs when systems are in Trunked production networks this is the case with most production environments.

.. note::
    It’s recommend connecting by remote console in IPMI because you may lose connection if you are SSH into the node

    1. ssh into each of your **AHV** Hosts
    2. Assign port br0 to the VLAN that you want the host be on.

    .. code-block:: bash
      ovs-vsctl set port br0 tag=host_vlan_tag

    3. Confirm VLAN tagging on port br0.

    .. code-block::
      ovs-vsctl list port br0

    3. From host console Log on to the **Controller VM**.

    .. code-block::
      ssh nutanix@192.168.5.254

    4. Assign the public interface of the **Controller VM** to a VLAN.
    .. code-block::
      change_cvm_vlan vlan_id

.. node::
    Hosts VLAN and CVM VLAN must be same.
