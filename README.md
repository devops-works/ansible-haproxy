haproxy Ansible playbook
========================

[![Travis
CI](http://img.shields.io/travis/devops-works/ansible-haproxy.svg?style=flat)](http://travis-ci.org/devops-works/ansible-haproxy)

This playbook will install haproxy 1.7+ and create multi config dir.

It also deploys janeczku ACME validation LUA script if
`haproxy_letsencrypt_manage` is set to yes. See
https://github.com/janeczku/haproxy-acme-validation-plugin for more
info. Note that lua script is installed in `/etc/haproxy/lua`, and certs
in `/etc/haproxy/certs`.

Requirements
------------

None

Role Variables
--------------

  - `haproxy_timeout_client`: Set the maximum inactivity time on the client side (default: 50000ms)
  - `haproxy_timeout_connect`: Set the maximum time to wait for a connection attempt to a server to succeed (default: 5000ms)
  - `haproxy_timeout_server`: Set the maximum inactivity time on the server side (default: 50000ms)
  - `haproxy_stats_bind_interface`: Interface to bind to for the stats front end (default: "*")
  - `haproxy_filter_allow_stats`: IP addresses to let in for the stats port (default: _none_, _required_)
  - `haproxy_stats_enable`: Whether stats are enabled (default: true)
  - `haproxy_stats_port`: Stats port (default: 8080)
  - `haproxy_stats_username`: Stats username (no defaults, role will fail if `haproxy_stats_enable` is set and `haproxy_stats_username` is not set)
  - `haproxy_stats_password`: Stats password (no defaults, role will fail if `haproxy_stats_enable` is set and `haproxy_stats_password` is not set)
  - `haproxy_letsencrypt_manage`: set to true to install LUA acme validation script (default:false)
  - `haproxy_letsencrypt_webroot`: webroot to use for acme validation (default: /var/tmp)
  - `haproxy_letsencrypt_email`: email for LetsEncrypt (default: _none_,
    _mandatory_)
  - haproxy_letsencrypt_logfile: logfile for renewal (default: none)

Tags
----

  - `haproxy` for the whole role
  - `haproxy:config` for the config files part

Dependencies
------------

None

Specs
-----

To run specs, issue:

```
vagrant up
vagrant ssh 'specs'
```

Example Playbook
----------------

TBD

License
-------

MIT

Author Information
------------------

@leucos
