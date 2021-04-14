# cookiecutter-ansible-playbook

Simple [cookiecutter](https://cookiecutter.readthedocs.io/en/latest/) template for Ansible playbook repos, including a Vagrant file for development and sample tests for GitLab CI and Travis.

## Usage

    $ cookiecutter gh:inhumantsar/cookiecutter-ansible-playbook
    year [2020]:
    project_name []:
    playbook_name []:
    inventory [inventory.txt]:
    python_version [3.8]:
    Select use_standard_roles:
    1 - yes
    2 - no
    Choose from 1, 2 [1]:
    author [nekeal]:
    author_github [nekeal]:
    company []:
    description [This playbook configures server and deploys ]:
    Select license:
    1 - BSD
    2 - MIT
    3 - GPLv3
    4 - Proprietary
    Choose from 1, 2, 3, 4 [1]:


### Vagrantfile

This does *not* use the Ansible provisioner as it's not usable on all Windows hosts. While most Windows hosts can be *managed* by ANsible, it is not possible (or at least not feasible) to install Ansible tools themselves on Windows hosts.

Instead, this Vagrantfile uses `shell` and `file` provisioners to install Ansible, copy the playbook to the path provided, and runs it with `ansible-playbook -v`.

To create the VM and run the playbook, use `vagrant up`.

To re-provision (re-copy and re-run the playbook), use `vagrant provision`.
