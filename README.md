YUUVIS API ANSIBLE ROLES
=========

Yuuvis api ansible roles for automated deployment of yuuvis api charts

Requirements
------------
...
ansible-galaxy collection install cloud.common
ansible-galaxy collection install kubernetes.core
ansible-galaxy collection install community.general
...

Role Variables
--------------
*namespace* : yuuvis -> Deployment target for momentum charts
*index* : 2 -> Index of keycloak-instance to deploy

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Usage
----------------
# Deploy infrastructure 
ansible-playbook playbook.yml --tags="linkerd,telemetry,cert-manager,ingress,infrastructure"
# Deploy additional keycloak instance 
ansible-playbook playbook.yml --tags="keycloak-instance" --extra-vars "index=${index}"
# Deploy momentum charts                                                                          
ansible-playbook playbook.yml --tags="yuuvis,proxy,client,bpm,rendition,management" --extra-vars "namespace=${NAMESPACE}"

License
-------

Copyright 2021 OPTIMAL SYSTEMS GmbH


Author Information
------------------
Thiemo Zevnik
zevnik@optimal-system.de
