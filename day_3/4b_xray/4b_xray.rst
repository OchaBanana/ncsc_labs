.. _4b_xray:


Lab 4b: X-Ray
*************

Install and Run X-Ray
---------------------

.. note:: If X-Ray is already deployed in your labs skip Steps 1-5

#. Download X-Ray from Nutanix Support Portal
#. Import the QCOW2 image v-disk into “Image Configurations” in AHV
#. Build a new VM with 8 vCPUs, 1 Core, and 8GB RAM
#. Clone the new disk from to Image Service
#. Add a NIC and power on VM
#. The VM should pickup an IP and you can browse to that IP to access XRAY
#. Run the “Four Corners Microbenchmark” tests to get an idea of just one of the many tests that X-RAY can provide. This should take about 20 minutes to run.
#. You can export the output to document and review the output.
