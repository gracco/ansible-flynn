ansible-flynn
=========

This role installs flynn in a cluster (minimum of 2 nodes)

https://flynn.io/

Requirements
------------

Ubuntu 16.04

Role Variables
--------------

flynn_master: flynn-master-node.acme  #Defines the master node
flynn_cluster_name: acme-cluster      # Defines the cluster name


Example Playbook
----------------
```
- hosts: flynn
  become: true
  tasks:
    - name: Influde flynn role
      include_role:
        name: flynn
      vars:
        flynn_master: flynn-master-node.acme
        flynn_cluster_name: acme-cluster
```

Exemple Inventory
-----------------
```
[flynn]
flynn01
flynn02
flynn03

[flynn_nodes]
flynn02
flynn03

```
Example Tests
------------

```
$ cd tests
$ vagrant up
$ ansible -v test.yml -i inventory

```
License
-------

BSD

Author Information
------------------

github.com/gracco
gracco.cerqueira@gmail.com
