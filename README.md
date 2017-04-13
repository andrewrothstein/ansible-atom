# ansible-atom

An Ansible role to install Atom Editor

## Requirements

- GCC
- python-devel
- redhat-rpm-config (on Fedora)

## Role Variables

defaults/main.yml

```
atom_ver : '1.2.3'
atom_mirror : 'https://github.com/atom/atom/releases/download'
atom_deb_platform : 'amd64'
atom_rpm_platform : 'x86_64'
```

vars/main.yml:

```
atom_deb : 'atom-{{atom_deb_platform}}.deb'
atom_deb_url : '{{atom_mirror}}/v{{atom_ver}}/{{atom_deb}}'

atom_rpm : 'atom.{{atom_rpm_platform}}.rpm'
atom_rpm_url : '{{atom_mirror}}/v{{atom_ver}}/{{atom_rpm}}'
```

## Dependencies

None

## Example Playbook

```
- hosts: all
  vars:
    atom_ver: 1.16.0
  roles:
    - role: ansible-atom
```

## Test

```
pip install molecule docker
molecule test
```

## License

MIT

## Author Information

<https://github.com/andrewrothstein>

## Contributor

<https://github.com/avnes>
