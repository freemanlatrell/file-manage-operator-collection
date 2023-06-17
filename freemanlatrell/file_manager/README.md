# File Manager Operator Collection <!-- omit from toc -->

The `file-manager` Operator Collection allows for the creation, deletion, and discovery of files on a host.

- [Playbooks](#playbooks)
  - [Create File](#create-file)
  - [Delete File](#delete-file)
  - [DiscoverFiles](#discoverfiles)
  - [FileMessage](#filemessage)
- [Reconfigure for Offline OpenShift environment](#reconfigure-for-offline-openshift-environment)


## Playbooks
The playbooks and CustomResources provided by this OperatorCollection are listed below.

### Create File
The `create_file` playbook is a simple example of executing a playbook to create a file on a target system.

- Create
    ```
    ansible-playbook playbooks/create_file.yml -i inventories/ibmcloud-vm.yml --limit ibmcloud-vm
    ```

### Delete File
The `delete_file` playbook is a simple example of executing a playbook to delete a file on a target system.

- Delete
    ```
    ansible-playbook playbooks/delete_file.yml -i inventories/ibmcloud-vm.yml --limit ibmcloud-vm
    ```

### DiscoverFiles
The `discover` playbook connects to a system and populates Kubernetes with File CustomResources

- Discover
    ```
    ansible-playbook playbooks/discover.yml -i inventories/ibmcloud-vm.yml --limit ibmcloud-vm
    ```

### FileMessage
The `file_message` playbook connects to a system and populates Kubernetes with File CustomResources

- Write to a file
    ```
    ansible-playbook playbooks/file_message.yml -i inventories/ibmcloud-vm.yml --limit ibmcloud-vm
    ```

## Reconfigure for Offline OpenShift environment
If you're currently running in an offline OpenShift cluster, you should install the [IBM Operator Collection SDK][oc-sdk], and run the following command to download the Ansible dependencies, and reconfigure this Operator Collection to use these local dependencies:

```bash
ansible-playbook ibm.operator_collection_sdk.create_offline_requirements
```


[oc-sdk]:https://github.com/IBM/operator-collection-sdk