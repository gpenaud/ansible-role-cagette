Role Name
=========

This role installs the cagette web-application, in haxe, with its sidecar mailer developped with
python and smtplib

Requirements
------------

For role testing:
  - molecule
  - podman
  - molecule[podman] driver

Role Variables
--------------

Mandatory environment variables:

  - HAXE_STD_PATH
  - HAXE_LIBCACHE
  - LD_LIBRARY_PATH
  - NEKOPATH
  - PATH
  - PROJECT_DIR

Defaults and overridable variables:

  install_directory: the cagette webapp instalaltion directory
  source_repository: the cagette webapp repository url
  nodejs_apt_repository_script_url: the node apt repository url (determine the nodejs versionto install)
  user: the cagette user by application and owner of related files and directories
  group: the cagette group by application and owner of related files and directories
  cagette_webapp_webserver_vhost_servername: the cagette webapp server name
  cagette_webapp_webserver_vhost_server_admin: the cagette webapp server admin
  cagette_webapp_webserver_tls_enabled: wether if TLS is enblad or not (HTTPS)
  cagette_webapp_webserver_tls_certificate_path: if TLS is enabled, set the certificate path
  cagette_webapp_webserver_tls_key_path: if TLS is enabled, set the certificate key path
  cagette_webapp_webserver_error_log_path: cagette webapp webserver error log path
  cagette_webapp_webserver_custom_log_path: cagette webapp webserver custom log path
  cagette_mailer_source_repository: the python mailer microservice source repository
  cagette_mailer_install_directory: the python mailer microservice installation directory


Dependencies
------------

  vars:
    - vars/main.yml
  roles:
    - role: geerlingguy.mysql

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).






# backend libraries
asys	  hscript      hxevents  smtpmailer  thx.csv	 tink_await  tink_http	tink_macro	tink_state     tink_syntaxhub	 utest
datetime  http-status  jwt	 templo      thx.semver  tink_chunk  tink_io	tink_multipart	tink_streams   tink_typecrawler
dbadmin   hx3compat    mime	 thx.core    tink_anon	 tink_core   tink_json	tink_priority	tink_stringly  tink_url

# backend + frontend libraries
asys	    haxe-lodash    hx3compat	 jwt		       react-next	       redux-connect  thx.core	  tink_chunk  tink_json       tink_state	tink_url
classnames  history	   hxevents	 material-ui	       react-router-4	       redux-thunk    thx.csv	  tink_core   tink_macro      tink_streams	utest
css-types   hscript	   hxleaflet	 mime		       react-transition-group  smtpmailer     thx.semver  tink_http   tink_multipart  tink_stringly
datetime    html-entities  jQueryExtern  modular	       react-types	       sugoi	      tink_anon   tink_hxx    tink_parse      tink_syntaxhub
dbadmin     http-status    js-object	 react-event-listener  redux		       templo	      tink_await  tink_io     tink_priority   tink_typecrawler

# podman instalaltion

python3 -m pip install --user "molecule[podman]"
16080  2022-05-05 14:06:38 python3 -m pip uninstall --user "molecule[podman]"
16087  2022-05-05 14:12:09 python3 -m pip uninstall "molecule[podman]"
16093  2022-05-05 14:47:11 molecule converge --driver-name podman
16094  2022-05-05 14:47:51 python3 -m pip install "molecule[podman]"
16095  2022-05-05 14:48:11 pip install podman
16096  2022-05-05 14:48:44 pip install molecule-podman
16097  2022-05-05 14:48:48 molecule test --driver-name podman
16098  2022-05-05 14:50:44 ansible-galaxy collection install containers.podman
