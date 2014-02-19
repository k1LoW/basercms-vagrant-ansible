# baserCMS Ansible provisioning in Vagrant

baserCMS環境をVagrant上にAnsibleを用いて構築するためのVagrantfile

## 必要環境

- VirtualBox
- Vagrant
 - ``centos6.5``という名前のCentOS 6.5のbox
- Ansible

## Vagrant上への構築方法

    $ vagrant up

## CentOS環境への構築方法

PovisionerのAnsibleを直接利用することで、VagrantではないCentOS環境へbaserCMSを構築することができます

以下はrootユーザのsshパスワードのみ分かっている状態(さくらVPSなど)を想定しています。

### 1.本番環境のInventory Fileを記述

``provision/vagrant`` を参考に ``provision/production``に必要情報を記述

### 2. ansible-playbookコマンドを実行

    $ ansible-playbook provision/site.yml -i provision/production -u root --ask-pass


