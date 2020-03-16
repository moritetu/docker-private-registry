Docker Private Registry
=======================

These are ansible playbooks to configure docker private registry.

Requirements
------------

* ansible

Setting
-------

### Edit Inventory file

Sets target nodes where services are installed.

### Certificate

Edit `group_vars/secure_registry.yaml`

```
registry:
  cert:
    subject:
      ...
```


Usage
-----

### Install docker secure registry

```
ansible-playbook -i hosts insecure-registry.yaml
```

### Install docker insecure registry

```
ansible-playbook -i hosts secure-registry.yaml
```

### Install docker client(podman)

Client for secure registry:

```
ansible-playbook -i hosts docker-cli-podman.yaml --extra-vars reg_type=secure_registry
```

Client for insecure registry:

```
ansible-playbook -i hosts docker-cli-podman.yaml --extra-vars reg_type=insecure_registry
```

