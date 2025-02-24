media_server
=========

This role sets up a media server and supporting services as docker containers.

Requirements
------------

This role requires the ansible docker community module.

    ansible-galaxy collection install community.docker

Role Variables
--------------

| Name                         | Comment                                                   | Default value  |
|------------------------------|-----------------------------------------------------------|----------------|
| media_server_tz | Timezone for the containers  | `Europe/Zurich` |
| media_server_username | Files and directories will be owned by this user. The media_server_appdata will also be setup in this users home directory as `media_server_username/docker`. Some containers will be started using this users UID. | `ansible` |
| media_server_groupname | Files and directories will be owned by this group. Some containers will be started using this GID. |`docker`|
| media_server_movies | Movie directory | `/media/movies` |
| media_server_tv | TV show directory | `/media/tv` |

Dependencies
------------

This role requires docker to be setup as in role-docker_setup.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    ---
    - name: Media server setup
    hosts: docker_hosts
    roles:
        - role: role-media_server

Service Descriptions
--------------------
Here’s a quick rundown of the services you can configure with this role, along with links to their official sites:

- [Portainer](https://www.portainer.io/) WebUI for managing your docker containers.
- [Dozzle](https://dozzle.dev/) Real-time Logging & Monitoring captures real-time Docker container logs, enabling quick and efficient issue diagnosis.
- [socket-proxy](https://github.com/Tecnativa/docker-socket-proxy) This is a security-enhanced proxy for the Docker Socket.
- [Homepage](https://github.com/gethomepage/homepage) A modern, fully static, fast, secure fully proxied, highly customizable application dashboard.
- [Emby](https://emby.media/index.html) Media server
- [sabnzbd](https://sabnzbd.org/) Free and easy binary newsreader
- [sonarr](https://sonarr.tv/) Sonarr is a PVR for Usenet and BitTorrent users.
- [radarr](https://radarr.video/) Radarr is a movie collection manager for Usenet and BitTorrent users.
- [bazarr](https://www.bazarr.media/) Bazarr is a companion application to Sonarr and Radarr. It manages and downloads subtitles.

License
-------

BSD
