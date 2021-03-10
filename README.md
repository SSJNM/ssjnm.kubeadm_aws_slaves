Role - Kubeadm AWS Slaves
=========

The role intends to configure a group of Kubernetes Slaves launched in AWS cloud

Requirements
------------

- Needs python-3.6+ with *boto* library installed in your system
- Make sure ssh_pass software is installed and host_key_check should be false in config file other wise we need to verify fingerprint 
- We need the file consisting of Slave joining command

Role Variables
--------------
There are some necessary variable that needs to be defined before using this role
Other variable that may be changed in future are also attached with (*defaults/main.yml*)

**Necessary variables:**

- *files_path:* Here we have to pass the folder location/directory where we want the token from  kubernetes master to be downloaded from master
-  Example --> files_path: /root/kubeadm_cloud/files/

Note:- The final path of files folder should be mentioned with / sign for directory. 

**Default variables:** These variables are not neccesary to be passed and will accept default values when nothing passed in var_file

Here we don't have any particular default variable to specify
 
Dependencies
------------

None

Example Playbook
----------------

Configuring the nodes under KubeSlaves ansible-group
With working directory to be /root/kubeadm_cloud/ and files/ folder conntaining the token

    - hosts: KubeSlaves
      vars:
        files_path: /root/kubeadm_cloud/files/
      roles:
         - role: ssjnm.kubeadm_aws_master


Author Information
------------------

This role was created by Nishant Singh, GitHub User - [SSJNM]

[SSJNM]: <https://github.com/SSJNM>