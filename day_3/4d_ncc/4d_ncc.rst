.. _4c_ncc:


Lab 4d: Nutanix Cluster Check (NCC)
***********************************

Run NCC
-------

#. SSH to CVM
#. Run 

   .. code-block:: bash

      ncc health_checks run_all

#. NCC output log: 

   .. code-block:: bash
   
      cat /home/nutanix/data/logs/ncc-output.log

#. Note how you can repeat and run individual tests. Identify how to gather resolution steps and solutions for your Fit Check report.