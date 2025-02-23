media_server
=========

This role sets up the arr-suite and media server in docker.

Requirements
------------

This role requires the ansible docker community module.

    ansible-galaxy collection install community.docker

Role Variables
--------------

| Name                         | Comment                                                   | Default value  |
|------------------------------|-----------------------------------------------------------|----------------|
| media_server_dir        | Directory used for docker containers to store their data. Uses the home directory of the user executing the ansible role. | `{{ ansible_facts['env']['HOME'] }}/docker`      |
| media_server_tz | Timezone for the containers  | `Europe/Zurich` |
| media_server_username | Files and directories will be owned by this user. | `ansible` |
| media_server_groupname | Files and directories will be owned by this group. |`docker`|

Dependencies
------------

This role requires docker to be setup as in role-docker_setup.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD
