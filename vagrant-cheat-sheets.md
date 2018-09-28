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
#### Default User Settings
**User**: vagrant
**Password**: vagrant

### Download Vagrant boxes manually
In this example, we're going to download the Midnight Sun box.
The box URL is https://app.vagrantup.com/uwmidsun/boxes/box/versions/2.1.0
In general, we just take the box URL, and then append the provider URL
https://app.vagrantup.com/<organization name>/boxes/<box name>/versions/<version>/providers/<provider>.box
wget https://app.vagrantup.com/uwmidsun/boxes/box/versions/2.1.0/providers/virtualbox.box -O box-2.1.0.box
Then you can add it to Vagrant
vagrant box add uwmidsun/box box-2.1.0.box
