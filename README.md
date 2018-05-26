Ubuntu 18.04 Vagrant box with Packer and Ansible
===============================================

Packer configuration thats build an Ubuntu 18.04 Vagrant box image and provisions it with Ansible.

## Requirements

You will need the following software is installed on your local machine:

* [Packer](http://www.packer.io/)
* [Virtualbox](https://www.virtualbox.org/)
* [Vagrant](http://vagrantup.com/)

[Ansible](http://docs.ansible.com/intro_installation.html) is used in the build process within VM (thats install Ansible), so you don't need this on your local machine.

## Usage

cd to the directory and run:

```SHELL
$ packer build ubuntu-18.04-vagrant.json
```

Note: If you are using Arch Linux in your local machine, replace packer command with packer-io


## Testing the machine image

The `Vagrantfile` included in this repository allows quick testing of the Virtualbox image built above. From the same directory, spin up a new Vagrant instance with the following command line:

```
$ vagrant up
```

## Tweaking the example

If you want to install additional software, instead to do with shell init scripts in Packer, you can do it through Ansible. An Ansible Playbook to add software is available in (`ansible/playbook.yml`).

For custom timezone, keyboard configuration and other installation things, you can edit (`ansible/playbook.yml`).   

## Testing boxes 

As you can see, there is not Vagrantfile (but you can add easily). So, you will need to add manually the box to Vagrant. Let's try:

```
$ vagrant box add ubuntu-18.04.box --name Ubuntu18-Ansible
```

## License

MIT / BSD
