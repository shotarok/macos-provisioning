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
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)
$ brew update

# install ansible
$ brew install ansible

# Install ansible collections
$ ansible-galaxy collection install community.general
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

## Special Thanks

### Repository/Module
- [geerlingguy/mac-dev-playbook](https://github.com/geerlingguy/mac-dev-playbook)
- [boxen/puppet-osx](https://github.com/boxen/puppet-osx)
- [kosssi/ansible-role-gitconfig](https://github.com/kosssi/ansible-role-gitconfig)

### References

- Mac の開発環境構築を自動化する (2015 年初旬編) http://t-wada.hatenablog.jp/entry/mac-provisioning-by-ansible
- HomebrewとAnsibleでMacの開発環境構築を自動化する http://mawatari.jp/archives/mac-provisioning-by-homebrew-and-ansible
- ansibleでmacの環境構築をつくります from fout.qiita.com
