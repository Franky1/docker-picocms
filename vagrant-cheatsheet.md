# Vagrant Cheatsheet

- Login/Password of default user is `vagrant/vagrant` usually - otherwise mentioned.

## Boxes

```shell
vagrant box add NAME
vagrant box list
vagrant box outdated --global
vagrant box update
vagrant box update --box NAME
vagrant box prune
vagrant box remove NAME
```

## Running

```shell
vagrant up
vagrant up --no-provision
vagrant reload
vagrant reload --provision
vagrant provision --provision-with shell
vagrant provision --provision-with file
vagrant provision --provision-with ansible_local
vagrant provision --provision-with prune
```

## Stopping

```shell
vagrant halt
vagrant destroy --force
```

## Status

```shell
vagrant version
vagrant validate
vagrant global-status
vagrant status
vagrant port
vagrant ssh
```

## Plugins

```shell
vagrant plugin list
vagrant plugin install NAME
vagrant plugin install vagrant-vbguest
```

## Vagrant Cloud

### Vagrant Boxes for VirtualBox

#### Ubuntu Bionic Beaver 18.04 Boxes

```shell
ubuntu/bionic64
bento/ubuntu-18.04
geerlingguy/ubuntu1804
```

#### Ubuntu Focal Fossa 20.04 Boxes

```shell
ubuntu/focal64
geerlingguy/ubuntu2004
bento/ubuntu-20.04
```

#### Debian 9 Stretch Boxes

```shell
debian/stretch64
geerlingguy/debian9
```

#### Debian 10 Buster Boxes

```shell
debian/buster64
geerlingguy/debian10
```

#### Centos 8 Boxes

```shell
centos/8
bento/centos-8
geerlingguy/centos8
```

#### Alpine Linux Boxes

```shell
generic/alpine312
```

### Add new Vagrant boxes

#### Ubuntu Bionic 18.04

```shell
vagrant box add ubuntu/bionic64
vagrant box add bento/ubuntu-18.04
vagrant box add geerlingguy/ubuntu1804
```

#### Ubuntu Focal Fossa 20.04

```shell
vagrant box add ubuntu/focal64
vagrant box add geerlingguy/ubuntu2004
vagrant box add bento/ubuntu-20.04
```

#### Debian 9 Stretch

```shell
vagrant box add debian/stretch64
vagrant box add geerlingguy/debian9
```

#### Debian 10 Buster

```shell
vagrant box add debian/buster64
vagrant box add geerlingguy/debian10
```

#### CentOS 8

```shell
vagrant box add centos/8
vagrant box add bento/centos-8
vagrant box add geerlingguy/centos8
```

#### Alpine Linux

```shell
vagrant box add generic/alpine312
```

### Update outdated boxes

```shell
vagrant box update --box ubuntu/bionic64
vagrant box update --box bento/ubuntu-18.04
vagrant box update --box geerlingguy/ubuntu1804

vagrant box update --box ubuntu/focal64
vagrant box update --box bento/ubuntu-20.04
vagrant box update --box geerlingguy/ubuntu2004

vagrant box update --box debian/stretch64
vagrant box update --box geerlingguy/debian9

vagrant box update --box debian/buster64
vagrant box update --box geerlingguy/debian10

vagrant box update --box centos/8
vagrant box update --box bento/centos-8
vagrant box update --box geerlingguy/centos8
```
