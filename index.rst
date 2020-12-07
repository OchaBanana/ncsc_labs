.. title:: NCSC Labs

.. toctree::
  :maxdepth: 2
  :caption: Lab 1 : Foundation Lab Remote installation
  :name: _day_1
  :hidden:

  day_1/1a_connect_ipmi/1a_connect_ipmi
  day_1/1b_using_crashcart/1b_using_crashcart
  day_1/1c_foundation_cvm/1c_foundation_cvm
  day_1/1d_1_click_upgrade/1d_1_click_upgrade
  day_1/1e_install_foudation/1e_install_foudation
  day_1/1f_install_pc/1f_install_pc
  day_1/1g_creating_built_guide/1g_creating_built_guide


.. toctree::
  :maxdepth: 2
  :caption: Day 2 Data Protection
  :name: _day_2
  :hidden:

  day_2/2a_bond_modes/2a_bond_modes
  day_2/2b_assigning_vlan/2b_assigning_vlan
  day_2/2c_snapshot/2c_snapshot
  day_2/2d_ssr/2d_ssr
  day_2/2e_replication/2e_replication

.. toctree::
  :maxdepth: 2
  :caption: Day 3 Data Migrations
  :name: _day_3
  :hidden:

  day_3/3a_manually_importing/3a_manually_importing
  day_3/3b_using_move/3b_using_move

.. toctree::
  :maxdepth: 2
  :caption: Day 3 Fit Checks Using Fit Check Tools
  :name: _day_3
  :hidden:

  day_3/4a_diagnostics/4a_diagnostics
  day_3/4b_xray/4b_xray
  day_3/4c_collector/4c_collector
  day_3/4d_ncc/4d_ncc

.. toctree::
  :maxdepth: 2
  :caption: Appendix
  :name: _appendix
  :hidden:

  tools_vms/windows_vm
 
.. _getting_started:

###############
Getting Started
###############

Welcome to the Nutanix NCS Labs!

The goal of the Knowledge Transfer Practical Exam is to generally show that you understand the product but more importantly that you are comfortable enabling your customers with the knowledge to administrate and manage their Nutanix cluster. You will be presenting just a sample of a Knowledge Transfer. For “talking points” You will be assigned Prism Functions randomly the night before via email. While you are presenting your Knowledge Transfer of about 10 minutes the rest of the class will play the role of the customer. They are encouraged to ask questions they may have or just to challenge the presenter with questions a customer would ask.

|

What's New
==========

- Workshop updated for the following software versions:
   - AOS 5.18.x
   - PC 2020.x

Agenda
======

- Day 1
   - Lab 1: Foundation Lab Remote installation
      - a: Connect to and using IPMI
      - b: Using the crashcart network_configuration command
      - c: Foundation from a CVM
      - d: 1-Click upgrade of AOS
      - e: Install Foundation VM on your Laptop (Optional reference Lab)
      - f: Install Prism Central
      - g: Creating an As Built Guide

- Day 2
   - Lab 2: Data Protection
      - a: Networking: Bond Modes in AHV
      - b: Networking: Assigning VLANs for Host & CVM (Optional reference Lab)
      - c: Snapshot Local and Recover
      - d: Self Service Restore SSR
      - e: Replication to remote site & recover snapshot remotely, Migrate and Activate. Snapshot to remote site

- Day 3
   - Lab 3: Data Migrations
      - a: Manually importing ESXi VMs to AHV (Optional reference Lab)
      - b: Using Move VMs to migrate from ESXi to AHV

   - Lab 4: Fit Checks Using Fit Check Tools
      - a: Diagnostics.py
      - b: X-Ray
      - c: Collector
      - d: Nutanix Cluster Check (NCC)


Introductions
=============

- Name
- Familiarity with Nutanix

Environment Details
===================

Each student will be assigned a Remote lab for at least 48hrs. You should get an email with all the IPs and logon Credentials to access your labs.

Lab Access Methods
==================

VPN option: Pulse Secure VPN Client
-----------------------------------

1. If client already installed skip to step 5
2. To download the client, login to https://xlv-uswest1.nutanix.com or https://xlv-useast1.nutanix.com using the supplied user credentials
3. Download and install client
4. Logout of the Web UI
5. Open client and **ADD** a connection with the following details:

For PHX:

  - **Type** - Policy Secure (UAC) or Connection Server
  - **Name** - X-Labs - PHX
  - **Server URL** - xlv-uswest1.nutanix.com

For RTP:

  - **Type** - Policy Secure (UAC) or Connection Server
  - **Name** - X-Labs - RTP
  - **Server URL** - xlv-useast1.nutanix.com

6. Once setup, login with the supplied credentials

Credentials
-----------

.. note::

  The *<Cluster Password>* is unique to each cluster and will be provided by the leader of the Workshop.

.. list-table::
  :widths: 25 35 40
  :header-rows: 1

  * - Credential
    - Username
    - Password
  * - Prism Element
    - admin
    - *<Cluster Password>*
  * - Prism Central
    - admin
    - *<Cluster Password>*
  * - Controller VM
    - nutanix
    - *<Cluster Password>*
  * - Prism Central VM
    - nutanix
    - *<Cluster Password>*

Each cluster has a dedicated domain controller VM, **DC**, responsible for providing AD services for the **NTNXLAB.local** domain. The domain is populated with the following Users and Groups:

.. list-table::
  :widths: 25 35 40
  :header-rows: 1

  * - Group
    - Username(s)
    - Password
  * - Administrators
    - Administrator
    - nutanix/4u
  * - SSP Admins
    - adminuser01-adminuser25
    - nutanix/4u
  * - SSP Developers
    - devuser01-devuser25
    - nutanix/4u
  * - SSP Operators
    - operator01-operator25
    - nutanix/4u
  * - SSP Consumers
    - consumer01-consumer25
    - nutanix/4u
  * - SSP Custom
    - custom01-custom25
    - nutanix/4u
