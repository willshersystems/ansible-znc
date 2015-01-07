ZNC
===

Install and configure a basic [znc](http://znc.in) server.

Requirements
------------

Tested on:

* Ubuntu 14.04 LTS

Role Variables
--------------

* **znc_datadir** is the directory under which ZNC configuration and data is stored. Defaults to */var/lib/znc*.
* **znc_upstart** is a boolean which controls the installation and starting of an upstart init config. Defaults to *true*.
* **znc_port** is an integer specificing the TCP port to listen on. Defaults to *8080*.
* **znc_ipv4** is a boolean, true to listen on IPv4. Defaults to *true*
* **znc_ipv6** is a boolean, true to listen on IPv6. Defaults to *false*
* **znc_ssl** is a boolean, true to enable SSL, false to disable. True will general a self-signed SSL certification if a certificate does not already exist. Defaults to *true*.
* **znc_user_name** ZNC user name. Defaults to *admin*
* **znc_user_password** ZNC user password. Defaults to SHA256 hash of password 'admin'.
* **znc_user_nick** ZNC admin users nick name. Defaults to *auser*
* **znc_user_altnick** ZNC admin users alt nick name. Defaults to **znc_user_nick_** (e.g. auser_)
* **znc_user_ident** ZNC admin users ident. Defaults to the nick.
* **znc_user_realname** ZNC admin users real name. Defaults to *Administrator*
* **znc_user_buffer** Channel buffer size. Defaults to *50*
* **znc_user_autoclearchanbuffer** auto clear the channel buffer on connect. Defaults to *true*

Dependencies
------------

None

Example Playbook
----------------

TBD

License
-------

LGPLv3

Author Information
------------------

Matt Willsher, matt@willsher.systems
