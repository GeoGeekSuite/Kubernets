Kubernetes
=========

A simple role to deploy MicroK8s on Ubuntu for demo purposes.

Requirements
------------

Use this role for Ubuntu 22.04 LTS

Role Variables
--------------

````
microK8s_addons: String that lists all MicroK8s addons that should be installed
ansible_user: Username of a user of the host system
manifest_folder: Folder in which manifests will be stored
local_registry:
  protocol: http or https
  url: Resolvable name of the host
  port: Port that is used for the MicroK8s registry (default is 32000)
gisnamespace: Kubernetes namespace for GIS related pods
````


Dependencies
------------

Example Playbook
----------------
````
- hosts: microk8s.test
  vars:
    microK8s_addons: 'dashboard dns ingress registry'
    ansible_user: marco
    manifest_folder: 'home/{{ ansible_user }}/manifests'
    local_registry:
      protocol: http
      url: microk8s.test
      port: 32000
    gisnamespace: gis
  roles:
  - { role: kube,
        tags: kube }
````

License
-------

Apache License Version 2.0

Author Information
------------------
Created by Marco Bradtke, contact via geogeeksuite.com
