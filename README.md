Ansible Role: Name Service Switch
=================================

Configures `/etc/nsswitch.conf`.


Table of Contents
-----------------

<!-- toc -->

- [Requirements](#requirements)
- [Role Variables](#role-variables)
- [Dependencies](#dependencies)
- [Example Playbook](#example-playbook)
  * [Top-Level Playbook](#top-level-playbook)
  * [Role Dependency](#role-dependency)
- [License](#license)
- [Author Information](#author-information)

<!-- tocstop -->


Requirements
------------

- Ansible 2.9


Role Variables
--------------

```yml
nsswitch_passwd:
  - files
  - sss

nsswitch_group:
  - files
  - sss

nsswitch_shadow:
  - files
  - sss
```


Dependencies
------------

```yml
---

# requirements.yml

roles:

  - name: idiv_biodiversity.nsswitch
    src: https://github.com/idiv-biodiversity/ansible-role-nsswitch
    version: vX.Y.Z

...
```


Example Playbook
----------------

### Top-Level Playbook

Write a top-level playbook:

```yml
---

- name: server
  hosts: group

  roles:
    - role: idiv_biodiversity.nsswitch
      tags:
        - nsswitch

...
```

### Role Dependency

Define the role dependency in `meta/main.yml`:

```yml
---

dependencies:

  - role: idiv_biodiversity.nsswitch
    tags:
      - nsswitch

...
```


License
-------

MIT


Author Information
------------------

This role was created in 2017 by [Christian Krause][author] aka [wookietreiber
at GitHub][wookietreiber], HPC cluster systems administrator at the [German
Centre for Integrative Biodiversity Research (iDiv)][idiv].


[author]: https://www.idiv.de/staff/christian-krause/
[idiv]: https://www.idiv.de/
[wookietreiber]: https://github.com/wookietreiber
