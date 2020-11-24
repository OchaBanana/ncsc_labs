.. title:: NCSC Labs

.. toctree::
  :maxdepth: 2
  :caption: NCSC Labs
  :name: _ncsc_labs
  :hidden:

  nscs/ncsc

.. toctree::
  :maxdepth: 2
  :caption: Day 1
  :name: _day_1
  :hidden:

  .. toctree::
    :maxdepth: 2
    :caption: Lab 1 : Foundation Lab Remote installation
    :name: _day_1
    :hidden:

  day_1/connect_ipmi/connect_ipmi
  day_1/using_crashcart/using_crashcart
  day_1/foundation_cvm/foundation_cvm
  day_1/1_click_upgrade/1_click_upgrade
  day_1/install_foudation/install_foudation
  day_1/install_pc/install_pc
  day_1/creating_built_guide/creating_built_guide


.. toctree::
  :maxdepth: 2
  :caption: Day 2 Data Protection
  :name: _day_2
  :hidden:

  day_2/bond_modes/bond_modes
  day_2/assigning_vlan/assigning_vlan
  day_2/snapshot/snapshot
  day_2/ssr/ssr
  day_2/replication/replication

.. toctree::
  :maxdepth: 2
  :caption: Day 3
  :name: _day_3
  :hidden:

  day_3/manually_importing/manually_importing
  day_3/using_move/using_move

.. toctree::
  :maxdepth: 2
  :caption: Day 3
  :name: _day_3
  :hidden:

  day_3/diagnostics/diagnostics
  day_3/xray/xray
  day_3/collector/collector
  day_3/ncc/ncc

.. toctree::
  :maxdepth: 2
  :caption: Era Rest APIs
  :name: _era_rest_apis
  :hidden:

  era_rest_api/era_rest_api

.. toctree::
  :maxdepth: 2
  :caption: Optional Labs
  :name: _optional_labs
  :hidden:



.. toctree::
  :maxdepth: 2
  :caption: Appendix
  :name: _appendix
  :hidden:

  appendix/glossary
  tools_vms/windows_tools_vm
  tools_vms/linux_tools_vm

.. _getting_started:

---------------
Getting Started
---------------

Welcome to the Nutanix NCS Labs!

The goal of the Knowledge Transfer Practical Exam is to generally show that you understand the product but more importantly that you are comfortable enabling your customers with the knowledge to administrate and manage their Nutanix cluster. You will be presenting just a sample of a Knowledge Transfer. For “talking points” You will be assigned Prism Functions randomly the night before via email. While you are presenting your Knowledge Transfer of about 10 minutes the rest of the class will play the role of the customer. They are encouraged to ask questions they may have or just to challenge the presenter with questions a customer would ask.

What's New
++++++++++

- Workshop updated for the following software versions:
    - AOS 5.18.x
    - PC 2020.x

Resources
+++++++++

- `Era Software Download <https://portal.nutanix.com/#/page/releases/eraDetails>`_
- `Era User Guide <https://portal.nutanix.com/#/page/docs/details?targetId=Nutanix-Era-User-Guide-v10:Nutanix-Era-User- Guide-v10>`_

Agenda
++++++

- Day 1 - Lab 1 : Foundation Lab Remote installation
    - a: Connect to and using IPMI
    - b: Using the crashcart network_configuration command
    - c: Foundation from a CVM
    - d: 1-Click upgrade of AOS
    - e: Install Foundation VM on your Laptop (Optional reference Lab)
    - f: Install Prism Central
    - g: Creating an As Built Guide

- Day 2 - Lab 2 : Data Protection
    - a: Networking: Bond Modes in AHV
    - b: Networking: Assigning VLANs for Host & CVM (Optional reference Lab)
    - c: Snapshot Local and Recover
    - d: Self Service Restore SSR
    - e: Replication to remote site & recover snapshot remotely, Migrate and Activate. Snapshot to remote site

- Day 3 - Lab 3 : Data Migrations
    - a: Manually importing ESXi VMs to AHV (Optional reference Lab)
    - b: Using Move VMs to migrate from ESXi to AHV

- Day 3 - Lab 4 : Fit Checks Using Fit Check Tools
    - a: diagnostics.py
    - b: X-Ray
    - c: Collector
    - d: Nutanix Cluster Check (NCC)


Introductions
+++++++++++++

- Name
- Familiarity with Nutanix

Initial Setup
+++++++++++++

- Take note of the *Passwords* being used.
- Log into your virtual desktops (connection info below)

Environment Details
+++++++++++++++++++

Nutanix Workshops are intended to be run in the Nutanix Hosted POC environment. Your cluster will be provisioned with all necessary images, networks, and VMs required to complete the exercises.

Networking
..........

Hosted POC clusters follow a standard naming convention:

- **Cluster Name** - POC\ *XYZ*
- **Subnet** - 10.**21**.\ *XYZ*\ .0
- **Cluster IP** - 10.**21**.\ *XYZ*\ .37

If provisioned from the marketing pool:

- **Cluster Name** - MKT\ *XYZ*
- **Subnet** - 10.**20**.\ *XYZ*\ .0
- **Cluster IP** - 10.**20**.\ *XYZ*\ .37

For example:

- **Cluster Name** - POC055
- **Subnet** - 10.21.55.0
- **Cluster IP** - 10.21.55.37

Throughout the Workshop there are multiple instances where you will need to substitute *XYZ* with the correct octet for your subnet, for example:

.. list-table::
  :widths: 25 75
  :header-rows: 1

  * - IP Address
    - Description
  * - 10.21.\ *XYZ*\ .37
    - Nutanix Cluster Virtual IP
  * - 10.21.\ *XYZ*\ .39
    - **PC** VM IP, Prism Central
  * - 10.21.\ *XYZ*\ .40
    - **DC** VM IP, NTNXLAB.local Domain Controller

Each cluster is configured with 2 VLANs which can be used for VMs:

.. list-table::
  :widths: 25 25 10 40
  :header-rows: 1

  * - Network Name
    - Address
    - VLAN
    - DHCP Scope
  * - Primary
    - 10.21.\ *XYZ*\ .1/25
    - 0
    - 10.21.\ *XYZ*\ .50-10.21.\ *XYZ*\ .124
  * - Secondary
    - 10.21.\ *XYZ*\ .129/25
    - *XYZ1*
    - 10.21.\ *XYZ*\ .132-10.21.\ *XYZ*\ .253

Credentials
...........

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
  * - SSP Power Users
    - poweruser01-poweruser25
    - nutanix/4u
  * - SSP Basic Users
    - basicuser01-basicuser25
    - nutanix/4u

Access Instructions
+++++++++++++++++++

The Nutanix Hosted POC environment can be accessed a number of different ways:

Parallels VDI
.................

Login to: https://xld-uswest1.nutanix.com (for PHX) or https://xld-useast1.nutanix.com (for RTP)

**Nutanix Employees** - Use your NUTANIXDC credentials
**Non-Employees** - **Username:** POCxxx-User01 (up to POCxxx-User20), **Password:** *<Provided by Instructor>*

Pulse Secure VPN
..........................

To download the client: login to https://xlv-uswest1.nutanix.com or https://xlv-useast1.nutanix.com - **Username:** POCxxx-User01 (up to POCxxx-User20), **Password:** *<Provided by Instructor>*

Download and install the client.

In Pulse Secure Client, **Add** a connection:

For PHX:

- **Type** - Policy Secure (UAC) or Connection Server
- **Name** - X-Labs - PHX
- **Server URL** - xlv-uswest1.nutanix.com

For RTP:

- **Type** - Policy Secure (UAC) or Connection Server
- **Name** - X-Labs - RTP
- **Server URL** - xlv-useast1.nutanix.com


Nutanix Version Info
++++++++++++++++++++

- **AHV Version** - AHV 20170830.185 (5.9+/5.10+)
- **AOS Version** - 5.10.2
- **PC Version** - 5.10.2
