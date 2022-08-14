Role Name
=========

A simple role to deploy MicroK8s on Ubuntu for demo purposes.

Requirements
------------

Use this role for Ubuntu 22.04 LTS

Role Variables
--------------

manifest_folder
gisnamespace
storage


Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

---
- hosts: local
  vars:
    manifest_folder: ~/geogeek_manifests
    gisnamespace: gis
    storage_base: ~/geogeek_storage
    storage:
    - name: test
      type: local
      path: '{{ storage_base }}/test'
      size: 1M
  roles:
  - { role: kube,
        tags: kube }


License
-------

Apache License Version 2.0

Author Information
------------------
Created by Marco Bradtke, contact via geogeeksuite.com
