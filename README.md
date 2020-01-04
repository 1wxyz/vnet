# <u>v</u>irtual <u>net</u>work (vnet) Kit

vnet is a simple tool to create bridge(s) or virtual network(s) on a linux machine.
It is inspired by lxc-net source code that creates lxcbr0 bridge for LXC containers.
It is fully written in bash which uses linux network modules available on the host machine.
It is independent of other services (e.g. host only adapter or vboxnet which is part of VirtualBox and will be removed if VirtualBox is uninstalled, a scenario when user decides to move from VirtualBox to say VMware/KVM.)
It supports containers, virtual machines (with the use of TAP adapter for VirtualBox/VMware virtual machines).

The virtual bridge currently supports two modes:
1. Bridged mode, where devices connected on the bridged will be forwarded the networks foreign to the bridge.
2. Isolated mode, where devices connected on the bridge will not be isolated within the bridge itself, with the execption of DNS resolution which will however be allowed to be resolved by the gateway of the bridge.

The vnet tool will be running in two modes, defined depending on its executing conditions:
1. Package mode, if vnet tool is say, cloned from a remote repo or extracted from a zip file from a trustworthy location and shall be used to setup vnet on the host machine.
2. Tool mode, if vnet tool has been installed onto the host machine, and the location where the tool is executed is the same as where it was defined during the installation process.
Thus, it is recommended to backup profiles, and install vnet using downloaded from a trustworthy location and then import the profiles after successful installation in case of OS re-image or moving to a new device.

# Features
- Allow multiple virtual network profiles.
- Uses dnsmasq as a DHCP server, DNS resolver/server.
- Allows Profile(s) to be started automatically on startup or by demand.
- Interactive profile management (new/edit/rename/delete).
- Profiles can be exported/imported for safe keeping or restoration/application on another device.
- Simple unicast MAC generator.
- TAP adapter module which is by default disabled and can be edited by running edit command to support virtual devices that couldn't see virtual bridges.

# Benefits

- Lightweight, customisable as they are all writen in bash.
- Supports multiple vnet profiles for individual needs.
- Easy to deploy, hopefully =).

# Installation

- Clone this repo from github or extract the vnet package.
- Navigate into `vnet` folder.
- Execute `./vnet install`.
- Follow the instructions there.

# Changes

They are all outlined [here](/CHANGELOG/)

# Special Thanks

- LXC developers, for giving me the idea to write these scripts.
