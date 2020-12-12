.. _1g_creating_built_guide:


Lab 1g: Creating an As Built Guide
**********************************

This is important lab after Nutanix cluster installation & configurations are completed one of most important deliverables is the “As Built Guide” documentation. Foundation.

Installation
------------

#. Copy and Extract the “**As_Built_Documenter**” from the Cluster Deployment Service Kit & Choose the appropriate script for your OS:
    * `Windows: Nutanix Cluster as Built <https://www.dropbox.com/s/q121g0o6y7ryutl/Nutanix_Cluster_as_Built_Windows_v4.8.1.zip?dl=1>`_
    * `Mac: Nutanix Cluster as Built <https://www.dropbox.com/s/jnpam9bsao3wzo4/Nutanix_Cluster_as_Built_Mac_v4.8.1.zip?dl=1>`_

Usage
-----

After the files have been unzipped:

.. note:: If running on MAC, use ./generate_document (needs path to execute)

.. note:: The MAC executable has been built on MAC OS version 10.13.6, so you can only run this executable on same or later versions of MAC OS.

:: Single cluster:
 ``generate_document.exe -c "Acme Barricades, Inc." -n <Nutanix cluster IP or FQDN>``

:: Multi cluster:
 ``generate_document.exe -c "Acme Barricades, Inc." -n "<Nutanix cluster 1>,<Nutanix cluster 2>"``

:: Multi cluster with multiple login credentials:
 ``generate_document.exe -c "Acme Barricades, Inc." -n "<Nutanix cluster 1>,<Nutanix cluster 2>" -m``

To input list of host IPs from file, use "-f" argument

.. note:: The input file is a YAML file which has all the IPs or FQDN listed under "nutanix_clusters" section

``generate_document.exe -c "Acme Barricades, Inc." -f <File containing Nutanix Cluster IP or FQDN>``

To generate output in excel workbook format, use "-e" argument

:: Single cluster:
 ``generate_document.exe -c "Acme Barricades, Inc." -n <Nutanix cluster IP or FQDN> -e``

:: Multi cluster:
 ``generate_document.exe -c "Acme Barricades, Inc." -n "<Nutanix cluster 1>,<Nutanix cluster 2>" -e``

:: Multi cluster with multiple login credentials:
 ``generate_document.exe -c "Acme Barricades, Inc." -n "<Nutanix cluster 1>,<Nutanix cluster 2>" -m -e``

For multi cluster, enter multiple Nutanix Cluster FQDNs or IPs seperated by commas surrounded by quotes.

.. note:: When running for multiple clusters, the IPs/FQDNs MUST be a comma delimited string enclosed by quotes.

To run with clusters that use AD credentials pass the AD login with domain.

``generate_document.exe -c "Acme Barricades, Inc." -n <Nutanix cluster IP or FQDN>``

When you run the executable, you will be prompted for the Nutanix cluster login and password.

.. note:: If running for multiple clusters the same user name and password can be used for all clusters that are passed into the automation. If there is a need to use separate user names and/or passwords for each cluster, pass the -m flag and you will beprompted for the credentials per each cluster.

.. note:: If running on older clusters that do expose all of the cluster components via the REST API, the script will continue toexecute and will display a message that the affected table will need to be updated manually.

A Word document will be the output of the execution. The document will be named with the following convention:

<customer name>-<Nutanix cluster name>-Nutanix_Cluster_as_Built-<date>-<time>.docx

:: Example:
Acme_Barricades_Inc-acmedevcluster-Nutanix_Cluster_as_Built_2016-11-23_112629.docx

Once the document has been created, open and update the TOC (Table of Contents) by right clicking on the TOC, selecting 'Update Field', then selecting 'Update Entire Table' and then click 'OK'.

Continue through the document filing in any information that could not be sourced from the Nutanix cluster, inserting the appropriate diagrams, reformatting as needed and removing any red text highlighted in yellow after completing instructed edits.

.. note:: There is also the possibility that the version of AOS that is on the cluster may not support certain Nutanix REST API
versions. In this case the script will create all of the tables with no data. These tables will need to be filled in manually or removed from the document before handing off to the customer.

When "-e" argument has been passed a excel workbook along with the word document will be the output of the execution. The workbook will be named with the following convention:

<customer name>-<Nutanix cluster name>-Nutanix_Cluster_as_Built-<date>-<time>.xlsx

:: Example:
Acme_Barricades_Inc-acmedevcluster-Nutanix_Cluster_as_Built_2016-03-03_212629.xlsx

vCenter Info Usage
------------------

Your /etc/hosts file should have the hostname and ip of vcenter server (if hostname is entered as input).
If you wish not to gather information from vCenter, use the below command:

``generate_document.exe -c "Acme Barricades, Inc." -n <Nutanix cluster IP or FQDN> -xv``

If you are running the tool against multiple ESXi clusters with multiple login credentials:

``generate_document.exe -c "Acme Barricades, Inc." -n "<Nutanix cluster 1>,<Nutanix cluster 2>" -mv``

To pass/change the default SSL Port number (443) used to login to vCenter, use:

.. note:: The default SSL Port Number used to connect to vCenter is 443.

``generate_document.exe -c "Acme Barricades, Inc." -n "<Nutanix cluster 1>" -pv``

Using Prism Central
-------------------

Use the following command to use PC credentials and generate outputs for all associated clusters.

``generate_document.exe -c test -pc 10.1.174.4``

Known Issues
------------

Mixed Clusters
++++++++++++++

Hypervisors

If the Nutanix cluster contains mixed hypervisors, e.g. AHV and ESXi, only the hypervisor host information for the first hypervisor found in the cluster will be documented. Please update the document manually for any additional hypervisors in the cluster.

Node Hardware

If the Nutanix cluster contains mixed hardware nodes, e.g. NX-3065-G5 and NX-8150-G5, only the image for the first node in the cluster will be captured in the document. Please update the document manually with the additional image(s).

UCS Hardware

If the Nutanix cluster is installed on UCS hardware, the UCS specific information will need to be added manually from the UCS build template document.

Protection Domains pre AOS 5.0

The protection domain information is not reliably available in AOS version pre 5.0.

Mac OS

The following error message is displayed when running from a Mac:

Failed to execute script generate_document

This is an erroneous message as the script does run successfully and the document(s) are created. This a bug with the tool used to package the executable which only presents on a Mac OS. The issue is noted and will be addressed as soon a fix is provided.

Argument help
-------------

.. raw:: html

  <p> usage: generate_document  &emsp;&emsp;&emsp;  [-h] -c CUSTOMER_NAME
  <br>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;(-n NUTANIX_CLUSTER_HOSTS | -pc PRISM_CENTRAL_HOSTS | -f NUTANIX_CLUSTER_FILE)
  <br>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;[-t DOCUMENT_TEMPLATE] [-s DATA_SOURCE]
  <br>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;[-l DOCUMENT_LAYOUT] [-wl WORKBOOK_LAYOUT] [-a]
  <br>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;[-e] [-es] [-w] [-m] [-d] [-mv] [-pv] [-xv]
  <p>
  <br>optional arguments:
  <br>&emsp;-h, --help &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;&nbsp;show this help message and exit
  <br>&emsp;-c CUSTOMER_NAME, --customer CUSTOMER_NAME
  <br>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;Customer name.
  <br>&emsp;-n NUTANIX_CLUSTER_HOSTS, --nutanix_cluster_hosts NUTANIX_CLUSTER_HOSTS
  <br>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;API host IP or FQDN.
  <br>&emsp;-pc PRISM_CENTRAL_HOSTS, --prism_central_hosts PRISM_CENTRAL_HOSTS
  <br>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;Prism Central IP or FQDN
  <br>&emsp;-f NUTANIX_CLUSTER_FILE, --nutanix_cluster_file NUTANIX_CLUSTER_FILE
  <br>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;File containing API host IP or FQDN.
  <br>&emsp;-t DOCUMENT_TEMPLATE, --document_template DOCUMENT_TEMPLATE
  <br>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;Word document template.
  <br>&emsp;-s DATA_SOURCE, --data_source DATA_SOURCE
  <br>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;YAML data source file.
  <br>&emsp;-l DOCUMENT_LAYOUT, --document_layout DOCUMENT_LAYOUT
  <br>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;YAML document layout file.
  <br>&emsp;-wl WORKBOOK_LAYOUT, --workbook_layout WORKBOOK_LAYOUT
  <br>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;Excel workbook layout file.
  <br>&emsp;-a, --all_outputs &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;&emsp;&ensp;&nbsp;&nbsp;Generates Word document, Excel workbooks per cluster and Summary Workbook.
  <br>&emsp;-e, --excel_output &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&thinsp;&thinsp;Generates Excel workbooks per cluster
  <br>&emsp;-es, --excel_summary &emsp;&emsp;&emsp;&emsp;&emsp;&ensp;&thinsp;Generates Excel Summary Workbook.
  <br>&emsp;-w, --word_output &emsp;&emsp;&emsp;&emsp;&nbsp;&emsp;&emsp;&nbsp;&ensp;&nbsp;Generates Word documents per cluster
  <br>&emsp;-m, --multi_user &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;&nbsp;Multiple user accounts are required to access multiple clusters.
  <br>&emsp;-d, --debug &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp;&nbsp;Debug the document generaton workflow
  <br>&emsp;-mv, --multi_user_vcenter &emsp;&emsp;&emsp;&nbsp;&nbsp;Multiple user accounts are required to access different vcenters.
  <br>&emsp;-pv, --ssl_port_vcenter &emsp;&emsp;&emsp;&emsp;&ensp;&nbsp;&nbsp;Non-standard vCenter SSL port
  <br>&emsp;-xv, --no_vcenter &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp;&nbsp;Exclude vCenter Info
  </p>

Documentation
-------------

#. Open File generated and modify the highlighted areas using provide templates to complete
    *Use your company document template if applicable – this would be if you are providing the installation service in behalf of your company*

Email this file to instructor this is part of your Practical Exam requirements
