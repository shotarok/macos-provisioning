![lint](https://github.com/shotarok/macos-provisioning/actions/workflows/lint.yml/badge.svg)

# Ansible Playbook to provision macOS

An ansible-playbook to provision my macOS.

## How to use

### Preparation

```console
# install command line tools
$ sudo xcodebuild -license
$ xcode-select --install

# install homebrew
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
$ brew update

# install ansible
$ brew install ansible

# Install ansible collections
$ ansible-galaxy collection install -r requirements.galaxy.yml
```

### Run all provisioning

```console
$ git clone git@github.com:shotarok/macos-provisioning.git .macos-provisioning
$ cd .macos-provisioning
$ ansible-playbook -i hosts -vv localhost.yml
```

### Run specific tasks
```console
# Show a list of tags
$ ansible-playbook -i hosts localhost.yml --list-tasks

# Run tasks tagged 'cask'
$ ansible-playbook -i hosts -vv localhost.yml --tags cask
```

## References

- [geerlingguy/mac-dev-playbook](https://github.com/geerlingguy/mac-dev-playbook)
- [boxen/puppet-osx](https://github.com/boxen/puppet-osx)
- [kosssi/ansible-role-gitconfig](https://github.com/kosssi/ansible-role-gitconfig)


