# My Own macOS Provisioning with Ansible

Ansible taks for my own macOS Provisioning

## How to use

### Preparation

```shell
# install command line tools
$ sudo xcodebuild -license
$ xcode-select --install
# install homebrew
$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
$ brew update
# install ansible
$ brew install ansible
```

### Run all provisioning

```shell
$ git clone git@github.com:shotarok/macos-provisioning.git .macos-provisioning
$ cd .macos-provisioning
$ git submodule update # for ansible-modules-extra
$ HOMEBREW_CASK_OPTS="--appdir=/Applications" ansible-playbook -i hosts -vv localhost.yml
```

### Run tagged tasks
```shell
# Check tasks and its tags
$ ansible-playbook -i hosts localhost.yml --list-tasks
# Run tasks tagged 'cask'
$ HOMEBREW_CASK_OPTS="--appdir=/Applications" ansible-playbook -i hosts -vv localhost.yml --tags cask
```

## Special Thanks

### Repository/Module
- [boxen/puppet-osx](https://github.com/boxen/puppet-osx)
- [kosssi/ansible-role-gitconfig](https://github.com/kosssi/ansible-role-gitconfig)

### Web page

- Mac の開発環境構築を自動化する (2015 年初旬編) http://t-wada.hatenablog.jp/entry/mac-provisioning-by-ansible
- HomebrewとAnsibleでMacの開発環境構築を自動化する http://mawatari.jp/archives/mac-provisioning-by-homebrew-and-ansible
- ansibleでmacの環境構築をつくります from fout.qiita.com
