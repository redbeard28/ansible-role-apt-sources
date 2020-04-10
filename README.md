ANSIBLE-ROLE-APT-SOURCES
====================

Ansible role install APT repos


## Howto use this role?
This role need to be include in a playbook. 

Call this **Galaxy** role  like this:

````bash
ansible-galaxy install -r requirements.yml 
````

Inside requirements.yml
````yaml

- src: redbeard28.apt_sources
````

More info => [Ansible Docs](https://docs.ansible.com/ansible-container/roles/access.html)

## Requirements

 * Ansible 2.9+


Role Variables
--------------

```yaml
---
repo_apt_key: ''
remove_other_repo: 'false'
remove_repos:
  - /etc/apt/sources.list

sources_filename: 'myrepos'

myURL: "http://internal.mirror.mydomain.intra"
list_repos:
  - 'deb [arch=amd64] {{ myURL }}/debian {{ ansible_distribution_release }} main contrib non-free'

```

Dependencies
------------

none

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: all
      roles:
         - { role: redbeard28.apt_sources, tags: repo }


Molecule testing framework
--------------------------

You can use molecule to test this role.
```bash
image=debian tag="buster" molecule converge 
image=debian tag="buster" molecule verify 
```

Author Information
------------------

Jeremie CUADRADO[¹](mailto:info@redbeard-consulting.fr) from redbeard-consulting
