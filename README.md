# docker_repo

Ansible role to install docker repository

## Requirements

- Ansible >= 2.7

### Supported platforms

- EL
  - 7
- Ubuntu
  - bionic
  - xenial

## Default role variables

| Name                 | Description      |  Type  |              Default              | Required |
| -------------------- | ---------------- |:------:|:---------------------------------:|:--------:|
| docker_repo__baseurl | URL path to repo | string | `{{ docker_repo__def_repo_url }}` |   True   |
| docker_repo__enabled | is repo enable   |  bool  |              `True`               |   True   |

**All default variables are described in [defaults/main.yml](defaults/main.yml) file.**

## Static role variables

This section describes static variables implemented in the role.



### centos variables

| Name                      |           Description           |  Type  | Default                                                       |
| ------------------------- |:-------------------------------:|:------:| ------------------------------------------------------------- |
| docker_repo__def_repo_url | def URL path to repo for centos | string | `https://download.docker.com/linux/centos/7/$basearch/stable` |

**All static centos variables are described in [vars/centos.yml](vars/centos.yml)**

### ubuntu variables

| Name                      |           Description           |  Type  | Default                                                               |
| ------------------------- |:-------------------------------:|:------:| --------------------------------------------------------------------- |
| docker_repo__def_repo_url | def URL path to repo for ubuntu | string | `https://download.docker.com/linux/ubuntu {{ ansible_lsb.codename }}` |

**All static ubuntu variables are described in [vars/ubuntu.yml](vars/ubuntu.yml)**

## Example Playbook

```yaml
    - hosts: all
      become: true
      roles:
        - role: zerodowntime.docker_repo
```

## License

[Apache License 2.0](LICENSE)

## Support

ZeroDowntime <ansible@zerodowntime.pl>
