ZNC
===

Install and configure a basic [znc](http://znc.in) server and optionally:

* Configure SSL either with a self-signed certificate or the given key and cert.
* Create an init script via the OS native method.
* Create configuration to apply firewall rules.

Requirements
------------

Tested on:

* Ubuntu 14.04 LTS

Role Variables
--------------

* znc_datadir

Data directory for ZNC. Defaults to  */var/lib/znc*

* znc_service

Configure a ZNC service, starting ZNC at boot. Defaults to *true*

* znc_force_config_refresh

If true, replace the ZNC configuration if it already exists. By default, the
configuration file is only generated if it doesn't exist. Defaults to *false*

### Networking

* znc_port

Port ZNC will listen on. Defaults to *8080*

* znc_ipv4

Listen on IPv4 addresses. Defaults to *true*

* znc_ipv6

Listen on IPv6 addresses. Defaults to *false*

### SSL

* znc_ssl

Enable SSL. If this is `true` and `znc_certificate_file` is not set, a
self-signed certificate will be generated. Defaults to *true*

* znc_ssl_certificate_file

Local path to an SSL certificate file which contains the SSL key followed by
certificate, then any intermediate certificates. Not defined by default

### Initial User

* znc_user_name

Default admin users name. Defaults to *admin*

* znc_user_password

The given users password in the form ZNC accepts in its password file. Can be
generated with `znc --makepass`. Defaults to
*sha256#cc7c4c7f5a6d137d40ead990630d15e0ba2b4a8fc17b69b9fb3ae09583326d43#y-lQcP*f3TeAar_,,fqq#*,
which is admin

* znc_user_nick

Defaults user IRC nickname. Defaults to *auser*.

* znc_user_altnick

Alternative IRC nickname for the default user. Defaults to *{{ znc_user_nick }}_*
i.e. `auser_`

* znc_user_ident

IDENT string. Defaults to *{{ znc_user_nick }}*, i.e. `auser`

* znc_user_realname

ZNC user's real name. Defaults to *Got ZNC?*

* znc_user_buffer

Number of lines to store in user's channel buffers when not connected to ZNC.
Defaults to *50*

* znc_user_autoclearchanbuffer

Clear the user's buffer on connection. Defaults to *true*

Dependencies
------------

None

Example Playbook
----------------

```yaml
---
- hosts: znc
  sudo: true
  roles:
    willshersystems.znc:
      znc_ssl_certificate_file: files/znc.pem
      znc_user_name: bob
      znc_user_nick: bob
```

License
-------

LGPLv3

Author Information
------------------

Matt Willsher, matt@willsher.systems

(c)2015 Willsher Systems
