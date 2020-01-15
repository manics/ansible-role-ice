Role Name
=========

[![Build Status](https://travis-ci.org/ome/ansible-role-ice.svg)](https://travis-ci.org/ome/ansible-role-ice)
[![Ansible Role](https://img.shields.io/ansible/role/41081.svg)](https://galaxy.ansible.com/ome/ice/)

Install Zeroc Ice.

On Ubuntu this only installs the Ice binaries and required libraries under `/opt/ice/bin` (note this is a symlink).


Role Variables
--------------

Optional (expert users only):
- `ice_install_devel`: Install Ice development packages, default `False`
- `ice_install_python`: Install Ice Python globally, default `False`
- `ice_python_wheel`: URL to a python wheel package to be installed, ignored on Ubuntu
  You can use this to provide a precompiled ice-py package for 3.6 as an alternative to automatically compiling from the source package.
- `ice_binaries_symlink_dest`: Symlink the Ice binaries required by OMERO into this directory e.g. `/usr/local/bin` (Ubuntu only, must exist, if empty don't create symlinks)


Notes
-----
Note that 3.6 requires ice-python to be installed using pip, and will result in the installation of several development tools and libraries unless `ice_python_wheel` is provided.


Example Playbook
----------------

    - hosts: localhost
      roles:
        - role: ome.ice


Author Information
------------------

ome-devel@lists.openmicroscopy.org.uk
