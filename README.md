cagette
=======

This role installs the cagette web-application, in haxe, with its sidecar mailer developped with
python and smtplib

Requirements
------------

For role testing:
  - molecule
  - podman
  - molecule[podman] driver

Molecule and podman installation

```
python3 -m pip install --user "molecule[podman]"
ansible-galaxy collection install containers.podman
```

Role Variables
--------------

Behavior enforcement variables:
```
  # cagette
  force_cagette_webapp_sources                force (re)installation of webapp sources
  force_cagette_webapp_compile_backend        force compilation of backend code through haxe
  force_cagette_webapp_compile_frontend       force compilation of frontend code through haxe
  force_cagette_webapp_dependencies_backend   force downloading dependencies for backend with lix
  force_cagette_webapp_dependencies_frontend  force downloading dependencies for frontend with lix
  force_cagette_webapp_templo                 force (re)installation and (re)run of haxelib and templo2
  # mailer
  force_cagette_mailer_source:                force (re)installation of mailer sources
```

Mandatory environment variables:
```
  HAXE_STD_PATH
  HAXE_LIBCACHE
  LD_LIBRARY_PATH
  NEKOPATH
  PATH
  PROJECT_DIR
```

Defaults and overridable variables:
```
  install_directory                              the cagette webapp instalaltion directory
  source_repository                              the cagette webapp repository url
  nodejs_apt_repository_script_url               the node apt repository url (determine the nodejs versionto install)
  user                                           the cagette user by application and owner of related files and directories
  group                                          the cagette group by application and owner of related files and directories
  cagette_webapp_webserver_vhost_servername      the cagette webapp server name
  cagette_webapp_webserver_vhost_server_admin    the cagette webapp server admin
  cagette_webapp_webserver_tls_enabled           wether if TLS is enblad or not (HTTPS)
  cagette_webapp_webserver_tls_certificate_path  if TLS is enabled, set the certificate path
  cagette_webapp_webserver_error_log_path        cagette webapp webserver error log path
  cagette_webapp_webserver_tls_key_path          if TLS is enabled, set the certificate key path
  cagette_webapp_webserver_custom_log_path       cagette webapp webserver custom log path
  cagette_mailer_source_repository               the python mailer microservice source repository
  cagette_mailer_install_directory               the python mailer microservice installation directory
```

Dependencies
------------
- role: geerlingguy.mysql

Example Playbook
----------------

License
-------

BSD

Author Information
------------------

- name: Guillaume Penaud
- mail: guillaume.penaud@gmail.com
- github: https://github.com/gpenaud

Notes
-----
