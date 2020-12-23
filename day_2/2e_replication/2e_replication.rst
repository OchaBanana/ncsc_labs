.. _2e_replication:


Lab 2e: Replication 
*******************

Replication to remote site & recover snapshot remotely, Migrate and Activate. Snapshot to remote site
-----------------------------------------------------------------------------------------------------

Create a Remote Site
--------------------

#. From Data Protection Click “**Remote Site**” and select “**Physical Cluster**”
#. Give Remote Site a name “<*Your Initials*-REMOTE>”
#. Choose Capabilities “**Disaster Recovery**” this will allow Remote Recovery
#. Enter the IP address of your partners cluster and choose “**Add Site**”
   .. note:: Please note, we will do partnerships between **Node-A<>Node-B**, **Node-C<>Node-D**

#. Choose Cluster to Cluster network mapping
#. Choose **vStore A to VStore B**.
#. Click **Save**

.. note::
  You must make a remote site from your partners cluster to your cluster and they should go from **vStore B to vStore A**.

Modify your Data Protection Group
---------------------------------

#. Select your Protection Domain and click update
#. Modify your Schedule and you will now see a remote site.
#. Keep last 30 on Remote site
#. Then Click “**Save**” the **Close**

Take a few snapshots
--------------------

#. Select your Protection Domain
#. Click “**Take Snapshot**”
#. Make sure the Remote site is selected and hit Save
#. Repeat step 2 & 3 a few times (at least 5 times)
#. The first replication should take the longest, click under “**Replications**” to watch the status.

Restoring from Remote snapshots:
--------------------------------

When Replications are done a full copy and its Deltas were sent to remote site.

Recover remote snapshot from local site A
  #. Select “**Remote Snapshots**”
  #. Select a remote snapshot to bring back as a local snapshot for local recovery

Snapshot to Remote Site & use Migrate/Activate
----------------------------------------------

Scenario #1 is you want to move the VM from site A to Site B.
  #. From Site A Select your Protection Domain **(Site A can be Node-A and Node-B at the same time)**
  #. Choose “**Migrate**” and notice all the VMs in that Protection Domain should be removed from Site A and powered on in Site B (Fail-Over)
  #. Feel free to continue work on the VM and make changes and repeat those steps 1&2 to migrate the Protection Domain back to Site A. (Fail-Back)

Scenario #2 is Site A has Failed and went down on its own you want to bring it back online in Site B
  #. Stop cluster at Site A **(Please do "cluster stop" only at Node-A and Node-C)**
  #. From Site B Select your Protection Domain
  #. Choose “**Activate**”
  #. This will bring the protection domain’s VMs online on remote site.
  #. When Site A is considered back online.
  #. ssh to cvm of Site A
  #. run ``ncli -h true``
  #. run ``pd deactivate_and_destroy_vms name=<PD_Name> force=true``
  #. Go back to Site B
  #. the **Migrate** button should now be able to send the latest back to Site
  #. Click "**Migrate**" to migrate all VMs in PD back to Site A


Snapshot to remote site
-----------------------

Recover a snapshot at Remote Site B
  #. From the site B look at “**local snapshots**”
  #. Recover one of your snapshots in Site B
