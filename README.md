Gotify
=========

Gotify is "a simple server for sending and receiving messages" (https://gotify.net/)
You can send messages via api. Can be used for messaging in an IoT environment.

There is also an Android app for receiving messages.

This role will install the Gotify server and enable a systemd service for it.

Requirements
------------

No requirements.

Role Variables
--------------

| Parameter                  | Default            | Description                                                               |
|----------------------------|--------------------|---------------------------------------------------------------------------|
| gotify_version             | 2.1.4              | The Gotify version to install (https://github.com/gotify/server/releases) |
| gotify_server_port         | 8080               | The server port Gotify is listening on. For now, must be > 1024           |
| gotify_admin_password      | random (25 chars)  | The default admin user                                                    |
| gotify_admin_usename       | admin              | The admin password                                                        |
| gotify_password_strength   | 10                 | The min. password length                                                  |
| gotify_enable_registration | false              | Should user registration be enabled?                                      |
| gotify_install_dir         | /opt/gotify        | Where to install Gotify                                                   |
| gotify_user                | gotify             | System user for Gotify server                                             |
| gotify_user_group          | gotify             | Group for system user ^^                                                  |
| gotify_bind_address        | <empty>            | The address to bind on (defaults to all)                                  |
| gotify_uploaded_images_dir | data/images        | The directory, where images are stored                                    |
| gotify_plugins_dir         | gotify_plugins_dir | The directory, where plugin resides                                       |

The admin password is saved in the config file. So, if you haven't set your own, you will have to log in to the target machine and get it there.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
          - role: pmoscode.gotify
            vars:
                gotify_version: 2.1.4
                gotify_admin_password: <verysecretpassword>

License
-------

MIT
