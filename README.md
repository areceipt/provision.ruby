# Provision.ruby
[![Galaxy](https://img.shields.io/badge/galaxy-provision.ruby-blue.svg?style=flat-square)](https://galaxy.ansible.com/khusnetdinov/provision.ruby/)

Repo forked from [Stouts.ruby](), work with updates. You can read more info about variables witch is not covered here.
This is ansible receipt for installing rbenv with ruby to linux (Ubuntu). It also is used in other [provision receipt](https://github.com/khusnetdinov/provisioner) for prepare production enviroment on server.

It install rbenv and after ruby to user.

#### Variables

```yaml
rbenv_version: v0.4.0         # rbenv version
rbenv_user: "deploy"          # rbenv user 
ruby_version: 2.2.2           # ruby version 
rbenv_root: /usr/local/rbenv  # rbvn root path
```

#### Usage

Add `provision.ruby` to your roles and set vars in your vars file or playbook file.

requirements file:

```yaml
- src: "https://github.com/areceipt/provision.ruby"
  name: ruby
```

vars_file:

```yaml
 env_version: v0.4.0
 rbenv_user: "deploy"
 ruby_version: 2.2.2
 rbenv_root: /usr/local/rbenv
```

playbook:

```yaml
- hosts: all
  roles:
  - role: ruby
    rbenv_user: "{{ deploy_user  }}"
    ruby_version: "{{ deploy_ruby_version  }}"
```
