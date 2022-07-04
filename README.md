YUUVIS API ANSIBLE ROLES
=========
Yuuvis api ansible roles for deploying yuuvis api charts

Requirements
------------
```
ansible-galaxy collection install cloud.common
ansible-galaxy collection install kubernetes.core
ansible-galaxy collection install community.general
```

Role Variables
--------------
Momentum namespace
**default** : *yuuvis*
```
namespace=yuuvis
```
Index of new keycloak Instance
```
*index* : 2 
```

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Usage
----------------
Deploying infrastructure services
```
ansible-playbook playbook.yml --tags="linkerd,telemetry,cert-manager,ingress,infrastructure"
```

Deploying new keycloak instance 
```
ansible-playbook playbook.yml --tags="keycloak-instance" --extra-vars "index=${index}"
```

Deploying momentum charts
```
ansible-playbook playbook.yml --tags="yuuvis,proxy,client,bpm,rendition,management" --extra-vars "namespace=${NAMESPACE}"
```

Deploying review charts
```
ansible-playbook playbook.yml --tags="review" --extra-vars "namespace=${NAMESPACE},chart=${CHART},chart_dir=${CHART_DIR}"
```

License
-------

Copyright 2021 OPTIMAL SYSTEMS GmbH


Author Information
------------------
Thiemo Zevnik
zevnik@optimal-system.de
