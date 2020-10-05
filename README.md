# ansible-role-splinter-extra-packages
Ansible role that provide extra packages installation for [Splinter provisioning tool](https://github.com/marcomc/splinter/), macOS setup automated with Ansible

# Usage
    vars:
      ruby_gems_packages_list_file: "files/lists/ruby_gems.txt"
      ruby_gems:
        - name: bundler
          state: present # present/absent/latest, default: present
          version: "~> 1.15.1"

      npm_global_packages_list_file: "files/lists/npm_global_packages.txt"

      npm_packages:
        - name: webpack
          state: present # present/absent/latest, default: present
          version: "^2.6"

      pip_packages_list_file: "files/lists/pip_packages.txt"

      pip_packages:
        - name: mkdocs
          state: present # present/absent/latest, default: present
          version: "0.16.3"

    roles:
      - role: marcomc.splinter_toolkit

    tasks:
      - name: Load the Splinter post provision tasks.
        include_role:
          name: marcomc.splinter_toolkit
          tasks_from: post-provision


# License & Copyright

License: [GPLv2](LICENSE.md)

2020 (c) Marco Massari Calderone <marco@marcomc.com>

# Credits

## Inspiration

geerlingguy's [Mac Development Ansible Playbook](https://github.com/geerlingguy/mac-dev-playbook)
