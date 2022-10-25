# Setting up your own DEVASC vm

> **Important:** this project is in no way affiliated with, or endorsed by Cisco. They provide a working vm that you can use in VirtualBox. Use at your own risk and don't blame me. This project is intended for powerusers that already have a devops/netops background.

## Tldr;

I am following the Cisco Devnet training and want to use the DEVASC vm. This vm is only provided for virtualbox and is incompatible with hyper-v, vmware esxi,...

This repo contains (almost) everything necessary to setup your own DEVASC vm.

## What doesn't work

- Packet tracer 7.4.0.T. There is no available package

## If you want to double check the requirements

Cisco provides you with a document that contains everything that is needed for the Devasc training. You can find this on netacad (after login) by going to `resources > all resources > Course Resources > DevNet Associate > v1.0 > English` and opening `DEVASC v1 VM Lab Environment FAQ.pdf`.

You can also use the direct link:

```
https://www.netacad.com/portal/resources/file/32496
```

## Setup

### Installing Linux Mint

At the time of this writing the devasc vm uses Linux mint Mate 20.04. You can download this here:

```
https://linuxmint.com/edition.php?id=293
```

Install this vm in your favourite virtualisation software. I recommend the following settings:

- 4 cpu
- 8GB ram
- 50GB disk (thin provisioned)

> **Note:** The cisco devasc vm uses the default user `devasc` with password `Cisco123!`. You do not need to set this up in your vm, the ansible script will take care of this.

### Setting up Linux mint for Ansible

So setup the vm we will be using Ansible. Ansible however requires Python to run. So there is a bit of a manual setup involved.

> **Note:** The Ansible playbook installs all listed requirements below. So if you already have a Ansible control node you do not need to perform the manual steps and you can just install all packages directly.

- Update the package list and upgrade packages where needed
  - This might take a while
- Install needed base packages
  - openssh-server
  - python3

```bash
sudo apt update ; sudo apt upgrade -y ; sudo apt autoremove

sudo apt install openssh-server ansible python3-pip -y
```

### Setting up the rest with Ansible

Now that you have a working installation of Ansible it is time to download the ansible playbook from this repo and use it to install everything else:

```bash
wget script
run script, provide username and pass
```



TODO

- add user to docker user group
- add user to sudo
- create devasc user and add to docker and sudo group
  - vscode repo + check for ansible cli install
- global install python modules