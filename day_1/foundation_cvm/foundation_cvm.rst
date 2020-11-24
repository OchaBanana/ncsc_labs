.. _foundation_cvm:

---------------------------------------------------------
Lab 1c: Foundation from a CVM
---------------------------------------------------------

Foundation software is installed on each CVM when they are imaged out of the factory. In some case the hardware is sold “Software Only” which means software must be installed “Baremetal”. In this case for remote installs Foundation will need to be installed on a local system in order to image the nodes. Please see also Baremetal steps in Field Installation Guide.

    .. role:: redtext
    1. Open a web browser to your CVM IP: http://<CVM IP:8000> :redtext:`***USE YOUR ASSIGNED CVM IP***`
    2. Page 1. Start fill form with your Assigned lab Network IP settings provided and hit “Next”
    3. Page 2. Nodes notice your remaining nodes should detect. Because they are previously configured the IPs autofilled but normally out of factory they will require you put your desired IPs. ONLY SELECT YOUR NODE IN THIS LAB. We will be making a single node cluster. Give it a Host name of HOST-<initials>.
    4. Page 3. Cluster page, let’s choose to “Skip automatic cluster formation” and give it 24GB of memory and hit “Next”. Note only a select few models are supported in Single-node cluster in foundation we will use “Skip” and do this manually since we do not have any single node models in the labs.
    5. On 4. AOS we will keep the default factory imaged software “we will skip AOS installation” and hit “Next”
