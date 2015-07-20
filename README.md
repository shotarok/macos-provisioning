# My OS X Provisioning

Ansible files for OS X Provisioning.

## How to use

### Preparation

```shell
# Install command line tools
$ sudo xcodebuild -license
$ xcode-select --install
# Install homebrew
$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
$ brew update
# install ansible
$ brew install ansible
```

### Run Provisioning

```shell
$ git clone git@github.com:Shtr28/osx-provisioning.git .osx-provisioning
$ cd .osx-provisioning
$ HOMEBREW_CASK_OPTS="--appdir=/Applications" ansible-playbook -i hosts -vv localhost.yaml
```

## Special Thanks
I appreciate following links:
- Mac の開発環境構築を自動化する (2015 年初旬編) http://t-wada.hatenablog.jp/entry/mac-provisioning-by-ansible
- HomebrewとAnsibleでMacの開発環境構築を自動化する http://mawatari.jp/archives/mac-provisioning-by-homebrew-and-ansible
- ansibleでmacの環境構築をつくります from fout.qiita.com
