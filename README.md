# ansible-role-pgcenter

[![Ansible Galaxy](https://img.shields.io/badge/galaxy-vitabaks.ansible__role__pgcenter-blue.svg)](https://galaxy.ansible.com/vitabaks/ansible_role_pgcenter/)

Install [pgCenter](https://github.com/lesovsky/pgcenter) (command-line admin tool for observing and troubleshooting PostgreSQL) with Ansible.


## Compatibility
All x86-64 Linux distributions.

pgCenter is written on Go language and distributed as a single precompiled binary file.

> pgCenter has been developed to work on Linux and hasn't been tested on other OS (operating systems), therefore, it is not recommended to use it on alternative systems because it will not operate properly.

## Role Variables
`pgcenter_version` - version of pgcenter package for installing. Default: `"0.6.2"`

`proxy_env` - use proxy server to download pgcenter packages (if required). Default: `[]`
###### example:
```
proxy_env:
  http_proxy: http://10.128.64.9:3128
  https_proxy: http://10.128.64.9:3128
```

###### optional variable:
`set_pgcenter_alias` - specify the alias for pgcenter ('false' or 'true'). Default: `'false'`
###### example:
```
alias pgcenter='pgcenter top -h /var/run/postgresql/ -U postgres -d postgres'
```

See the defaults/[main.yml](./defaults/main.yml) file for details.


## Dependencies
None.

## Example Playbook

    - hosts: servers
      roles:
         - role: ansible-role-pgcenter


## License
Licensed under the MIT License. See the [LICENSE](./LICENSE) file for details.


## Author Information
Vitaliy Kukharik (PostgreSQL DBA) vitabaks@gmail.com
