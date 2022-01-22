# k8-ansible-playbooks

## Overview

This git repository demonstrates Ansible playbooks to create kubernetes objects in Kubernetes/OpenShift cluster.

## Pre-requisites

- Install Ansible

- To create k8 objects ansible `k8s` modules is used. This is part of ansible package. It is not included in ansible-core. Make sure the `kubernetes.core` collection is installed be running below command:
``
ansible-galaxy collection list
``
- Install it using the command:
``
 ansible-galaxy collection install kubernetes.core
 ``

- The module has following requirements. These need to be installed as well
	python >= 3.6
    kubernetes >= 12.0.0
    PyYAML >= 3.11
    jsonpatch

## Playbook execution

By default k8s module uses the cluster details available in kubeconfig file present at  `~/.kube/config`. Hence login to the cluster using `oc login` command or `kubectl login` before executing the playbook.

To create K8 objects - Namespace, Pod and a Deployment in the cluster run the following playbook:

``ansible-playbook k8-demo-deployment.yaml``

To delete all the K8 object created, run the following playbook:

``ansible-playbook k8-demo-undeploy.yaml``

