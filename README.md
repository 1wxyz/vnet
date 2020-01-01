# <u>v</u>irtual <u>net</u>work (vnet) Kit

vnet is a simple tool to create bridge(s) or virtual network(s) on a linux machine.
It is inspired by lxc-net source code that creates lxcbr0 bridge for LXC containers.
It is fully written in bash which uses linux network modules available on the host machine.
It is independent of other services (e.g. host only adapter or vboxnet which is part of VirtualBox and will be removed if VirtualBox is uninstalled, a scenario when user decides to move from VirtualBox to say VMware/KVM.)
It supports containers, virtual machines (with the use of TAP adapter for VirtualBox/VMware virtual machines).

The bridge currently supports two modes:
1. Bridged mode, where devices connected on the bridged will be forwarded the networks foreign to the bridge.
2. Isolated mode, where devices connected on the bridge will not be isolated within the bridge itself, with the execption of DNS resolution which will however be allowed to be resolved by the gateway of the bridge.

# Features

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
