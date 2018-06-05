Hubot
=====

Ansible Role to setup Hubot

Role Variables
--------------

| Variable | Default | Definition |
|----------|---------|------------|
| hubot_adapter | slack | Adapter to be used |
| hubot_slack_token | | Token to use for Slack integration |
| hubot_admin | User <user@domain.com> | Admin contact |
| hubot_home | /var/lib/hubot | Where to run Hubot from |
| hubot_name | bot | Bot's name, this can **NOT** be `hubot`|
| hubot_version | 1.0.0 | Version of the bot, this will force to re-run the bot initilization if changed, only change with caution |
| hubot_description | Hubot | Bot's description |
| hubot_user | botuser | User to run Hubot as |
| hubot_group | botgroup | Default group for the Hubot user |
| hubot_hubot_pkgs | [] | Additional packages to be used by Hubot |
| hubot_adapter_environment_variables | | Environment variables to be set if adapter is not slack.  |

Example **requirements.yml** file
----------------

``` yaml
- src: https://github.com/adambirds/ansible-role-hubot.git
  name: ansible-role-hubot
```

Example Playbook if using Slack as your adapter
----------------

``` yaml
- hosts: hubot-servers
  roles:
    - role: ansible-role-hubot
      hubot_adapter: slack
      hubot_slack_token: token12345
      hubot_admin: Joe Bloggs <joe@example.com>
      hubot_home: /home/joe/hubot
      hubot_name: joe-hubot
      hubot_version: 1.0.0
      hubot_description: A helpful robot for your company
      hubot_user: joehubotuser
      hubot_group: joehubotgroup
```

Example Playbook if using not using Slack as your adapter
----------------

Please consult your adapter's documentation to see what environment variables you need setting.

``` yaml
- hosts: hubot-servers
  roles:
    - role: ansible-role-hubot
      hubot_adapter: campfire
      hubot_admin: Joe Bloggs <joe@example.com>
      hubot_home: /home/joe/hubot
      hubot_name: joe-hubot
      hubot_version: 1.0.0
      hubot_description: A helpful robot for your company
      hubot_user: joehubotuser
      hubot_group: joehubotgroup
      hubot_adapter_environment_variables: |
        HUBOT_CAMPFIRE_ACCOUNT=
        HUBOT_CAMPFIRE_TOKEN=
        HUBOT_CAMPFIRE_ROOMS=
```

License
-------

GPLv3

Author Information
------------------

Adam Birds