[![Build Status](https://travis-ci.org/shotarok/macos-provisioning.svg?branch=master)](https://travis-ci.org/shotarok/macos-provisioning)

# My Own macOS Provisioning with Ansible

Ansible taks for my own macOS Provisioning

## How to use

### Preparation

```console
# install command line tools
$ sudo xcodebuild -license
$ xcode-select --install

# install homebrew
$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
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

### Run tagged tasks
```console
# Check tasks and its tags
$ ansible-playbook -i hosts localhost.yml --list-tasks

# Run tasks tagged 'cask'
$ ansible-playbook -i hosts -vv localhost.yml --tags cask
```

## Special Thanks

### Repository/Module
- [geerlingguy/mac-dev-playbook](https://github.com/geerlingguy/mac-dev-playbook)
- [boxen/puppet-osx](https://github.com/boxen/puppet-osx)
- [kosssi/ansible-role-gitconfig](https://github.com/kosssi/ansible-role-gitconfig)

### Web page

- Mac の開発環境構築を自動化する (2015 年初旬編) http://t-wada.hatenablog.jp/entry/mac-provisioning-by-ansible
- HomebrewとAnsibleでMacの開発環境構築を自動化する http://mawatari.jp/archives/mac-provisioning-by-homebrew-and-ansible
- ansibleでmacの環境構築をつくります from fout.qiita.com
