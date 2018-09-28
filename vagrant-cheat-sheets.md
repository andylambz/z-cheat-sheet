# Vargant Cheat Sheet

```sh
vagrant -v
vagrant -help
```

```sh
vagrant init centos/7
vagrant up
vagrant status 
vagrant ssh
vagrant halt
vagrant reload
```

```sh
vagrant box add --name my-box /path/to/the/new.box
vagrant box list
vagrant package --output mynew.box
vagrant destroy
```

[========]

#### Default User Settings
> **User**: vagrant
**Password**: vagrant

[========]

### Download Vagrant boxes manually
Template URL:
https://app.vagrantup.com/<organization name>/boxes/<box name>/versions/<version>/providers/<provider>.box
Sample URL:
https://app.vagrantup.com/centos/boxes/7
Direct URL;
https://app.vagrantup.com/centos/boxes/7/versions/1804.02/providers/virtualbox.box
