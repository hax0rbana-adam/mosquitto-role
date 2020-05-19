alemuro.mosquitto
=========

This role installs and manages the Mosquitto service on Raspbian devices

Role Variables
--------------

| Name                                | Default                 | Description                                                                         |
|-------------------------------------|-------------------------|-------------------------------------------------------------------------------------|
| `alemuro_mosquitto_install_clients` | *yes*                   | `yes` if you wanna install the `mosquitto-clients` package                          |
| `alemuro_mosquitto_settings`        |                         | Object with parameters you wanna configure on mosquitto                             |
| `alemuro_mosquitto_password_file`   | */etc/mosquitto/pwfile* | Location of the passwords file                                                      |
| `alemuro_mosquitto_user_list`       |                         | Users object. One entry per user, with username as identifier and htpasswd as value |

**alemuro_mosquitto_settings**

```
alemuro_mosquitto_settings:
  allow_anonymous: no
  persistence: yes
  log_timestamp: yes
  log_timestamp_format: "%Y-%m-%dT%H:%M:%S"
```

**alemuro_mosquitto_user_list**

```
alemuro_mosquitto_settings:
  admin: <htpasswd value>
```

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```
    - hosts: pi
      roles:
         - { role: alemuro.mosquitto }
```

Usage
-----

* Install:

```
$ ansible-galaxy -p roles alemuro.mosquitto
```


License
-------

Apache License
