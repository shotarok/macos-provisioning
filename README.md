# My OS X Provisioning

Ansible files for OS X Provisioning.

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
$ git clone git@github.com:Shtr28/osx-provisioning.git .osx-provisioning
$ cd .osx-provisioning
$ git submodule update # for ansible-modules-extra
$ HOMEBREW_CASK_OPTS="--appdir=/Applications" ansible-playbook -M ./ansible-modules-extras/system -i hosts -vv localhost.yaml
```

### Run tagged tasks
```shell
# Check tasks and its tags
$ ansible-playbook -i hosts localhost.yaml --list-tasks
# Run tasks tagged 'cask'
$  HOMEBREW_CASK_OPTS="--appdir=/Applications" ansible-playbook -i hosts -vv localhost.yaml --tags cask
```

## Special Thanks
I appreciate following resources.

### Repository/Module
- [boxen/puppet-osx](https://github.com/boxen/puppet-osx)
- [kosssi/ansible-role-gitconfig](https://github.com/kosssi/ansible-role-gitconfig)

### Web page

- Mac の開発環境構築を自動化する (2015 年初旬編) http://t-wada.hatenablog.jp/entry/mac-provisioning-by-ansible
- HomebrewとAnsibleでMacの開発環境構築を自動化する http://mawatari.jp/archives/mac-provisioning-by-homebrew-and-ansible
- ansibleでmacの環境構築をつくります from fout.qiita.com
