[![release](https://github.com/darkwizard242/ansible-role-lens/workflows/release/badge.svg)](https://github.com/darkwizard242/ansible-role-lens/actions?query=workflow%3Arelease) ![Ansible Role](https://img.shields.io/ansible/role/56851?color=dark%20green%20) ![Ansible Role](https://img.shields.io/ansible/role/d/56851?label=role%20downloads) ![Ansible Quality Score](https://img.shields.io/ansible/quality/56851?label=ansible%20quality%20score) ![GitHub tag (latest SemVer)](https://img.shields.io/github/tag/darkwizard242/ansible-role-lens?label=release) ![GitHub repo size](https://img.shields.io/github/repo-size/darkwizard242/ansible-role-lens?color=orange&style=flat-square)

# Ansible Role: lens

Role to install (_by default_) [Lens](https://k8slens.dev/) on **Debian/Ubuntu** and **EL** systems. Lens is one of the most popular opensource Kubernetes IDE.

## Requirements

None.

## Role Variables

Available variables are listed below (located in `defaults/main.yml`):

### Variables list:

```yaml
lens_app: lens
lens_desired_state: present
lens_version: 5.3.3

# For Debian/Ubuntu Family
lens_debian_url: "https://api.k8slens.dev/binaries/Lens-{{ lens_version }}-latest.20211214.2.amd64.deb"

# For EL Family
lens_el_url: "https://api.k8slens.dev/binaries/Lens-{{ lens_version }}-latest.20211214.2.x86_64.rpm"
```

### Variables table:

Variable           | Description
------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------
lens_app           | Defines the app to install i.e. **lens**
lens_desired_state | Defined to dynamically chose whether to install (i.e. either `present` or `latest`) or uninstall (i.e. `absent`) the package. Defaults to `present`.
lens_version       | Defined to dynamically fetch the desired version to install. Defaults to: **5.3.3**
lens_debian_url    | Defines URL to download the 'deb' package from for Debian/Ubuntu family systems.
lens_el_url        | Defines URL to download the 'rpm' package from for EL family systems.

## Dependencies

None

## Example Playbook

For default behaviour of role (i.e. installation of **lens**) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.lens
```

For customizing behavior of role (i.e. specifying the desired **lens** version) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.lens
  vars:
    lens_version: 4.2.5
```

For customizing behavior of role (i.e. uninstallation of **lens** package) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.lens
  vars:
    lens_desired_state: absent
```

## License

[MIT](https://github.com/darkwizard242/ansible-role-lens/blob/master/LICENSE)

## Author Information

This role was created by [Ali Muhammad](https://www.alimuhammad.dev)
