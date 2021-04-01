# This is a **WIP** role

# sap-netweaver-ha-pacemaker
HA configuration of pacemaker for SAP Netweaver software 

### Role variables

| variable | info | required? |
|:--------:|:----:|:---------:|
|sap_netweaver_ha_pacemaker_hacluster_manage_shared_storage|Attempt to manage shared (eg. nfs) storage?|no, default is yes|
|sap_netweaver_ha_pacemaker_hacluster_node1_ip|IP address of first node in cluster|yes|
|sap_netweaver_ha_pacemaker_hacluster_node1_fqdn|FWDN of first node in cluster|yes|
|sap_netweaver_ha_pacemaker_hacluster_node2_ip|IP address of second node in cluster|yes|
|sap_netweaver_ha_pacemaker_hacluster_node2_fqdn|FWDN of second node in cluster|yes|
|sap_netweaver_ha_pacemaker_hacluster_manage_shared_storage|Default: yes. Should cluster manage storage resources?|yes|
|sap_netweaver_ha_pacemaker_hacluster_manage_azure_lb|Default: no. Deal with Azure load balancer?|no|
|sap_netweaver_ha_pacemaker_sid|SID of this instance|yes|
|sap_netweaver_ha_pacemaker_profile_path|Full path of directory holding profiles|no, is generated sanely|
|sap_netweaver_ha_pacemaker_ascs_instance_name|ASCS instance name|yes|
|sap_netweaver_ha_pacemaker_ascs_instance_number|ASCS instance number|yes|
|sap_netweaver_ha_pacemaker_ascs_profile_file|Full path and name of ASCS profile|no, is generated sanely|
|sap_netweaver_ha_pacemaker_ascs_profile_path|Full path of directory holding ASCS profile|
|sap_netweaver_ha_pacemaker_ascs_vip|Virtual (cluster managed) IP address for ASCS|yes|
|sap_netweaver_ha_pacemaker_ers_instance_name|ERS Instance name|yes|
|sap_netweaver_ha_pacemaker_ers_instance_number|ERS instance number|yes|
|sap_netweaver_ha_pacemaker_ers_profile_file|Full path and file name of ASCS profile|no, is generated sanely|
|sap_netweaver_ha_pacemaker_ers_profile_path|Full path of directory holding ASCS profile|
|sap_netweaver_ha_pacemaker_ers_vip|Virtual (cluster managed) IP address for ASCS|yes|
|sap_netweaver_ha_pacemaker_e4s_repos_ppc64le||no|
|sap_netweaver_ha_pacemaker_e4s_repos_x86_64||no|
|sap_netweaver_ha_pacemaker_instance_number|????? azure lb uses|???|
|sap_netweaver_ha_pacemaker_fs_ascs|???|???|
|sap_netweaver_ha_pacemaker_fs_ers|???|???|
|sap_netweaver_ha_pacemaker_fs_sapmnt|???|???|
|sap_netweaver_ha_pacemaker_fs_sys|???|???|
|sap_netweaver_ha_pacemaker_fs_trans|???|???|


 ## TODO and Notes
* This remains mostly untested against a range of systems.
* Var docs
* FS paths should match samples from docs
* Is this the right place for Azure LB?
* If using clustering, the sap_s4hana_deployment is likely going to need the hosts setup, so this is a dupe
* /etc/hosts perhaps should have ansible tags in it, either way, so the several roles can not clobber each other