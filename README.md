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
| docker_dir        | Directory used for docker containers to store their data. Uses the home directory of the user executing the ansible role. | `{{ ansible_facts['env']['HOME'] }}/docker`      |
| docker_tz | Timezone for the containers  | `Europe/Zurich` |

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
