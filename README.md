Hubot
=====

Role to setup Hubot

Requirements
------------

- none

Role Variables
--------------

| Variable | Default | Definition |
|----------|---------|------------|
| hubot_adapter | slack | Adapter to be used |
| hubot_slack_token | | Token to use for Slack integration |
| hubot_admin | User <user@domain.com> | Admin contact |
| hubot_home | /var/lib/hubot | Where to run Hubot from |
| hubot_name | bot | Bot's name |
| hubot_version | 1.0.0 | Version of the bot |
| hubot_description | Hubot | Bot's description |
| hubot_user | botuser | User to run Hubot as |
| hubot_group | botgroup | Default group for the Hubot user |
| hubot_hubot_pkgs | [] | Additional packages to be used by Hubot |
| hubot_hubot_scripts | [] | Cusom script files to copy |

Dependencies
------------

- ansible-role-user-setup

Example Playbook
----------------

```
- hosts: servers
  roles:
    - role: ansible-role-hubot
      hubot_slack_token: token12345
```

License
-------

GPLv3

Author Information
------------------

Adam Birds