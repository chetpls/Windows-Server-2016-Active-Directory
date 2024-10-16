# WINDOWS SERVER 2016 | Hands-On Virtual Labs

## Table of Contents
- [Overview](#overview)
- [Infrastructure](#infrastructure)
- [Domain Setup](#domain-setup)
- [Active Directory Management](#active-directory-management)
- [Key Tasks Completed](#key-tasks-completed)
- [Program Walk-through](#program-walk-through)
  - [Windows Server 2016 / Active Directory Installation](#windows-server-2016--active-directory-installation)
  - [Setting up Desktop1 / helpdesk](#setting-up-desktop1--helpdesk)
- [Notes](#notes)

## Overview

This homelab environment provides a practical setup for learning and experimenting with Windows Server 2016 administration, Active Directory management, and network infrastructure.

## Infrastructure

- **Hypervisor**: VirtualBox
- **Primary Server OS**: Windows Server 2016
- **Resource Optimization**: Linked clones
- **Remote Access**: Remote Desktop Protocol (RDP) enabled

## Domain Setup

- Windows 10 client machines joined to the Windows Server 2016 domain
- Server configured with custom name and TCP/IP settings

## Active Directory Management

- Created and modified template user accounts with various properties
- Implemented and linked Group Policy Objects (GPOs)

## Key Tasks Completed

1. Installed and set up VirtualBox, Windows Server 2016, linked clones, and RDP
2. Added Windows 10 client machines to Windows Server 2016 domain
3. Created and modified Active Directory template user accounts to hold various properties
4. Configured Windows Server 2016 domain settings, server name, TCP/IP settings, and remote desktop
5. Created and linked group policy objects in Active Directory

## Program Walk-through

### Windows Server 2016 / Active Directory Installation

1. Install Windows Server 2016:
   ![Install Windows Server 2016](https://media.discordapp.net/attachments/1295155312151625748/1295155496633897090/image.png?ex=6710eacd&is=670f994d&hm=73f21d19f9176705ec4b78a6d5764cfb3486f918b2c747b8083d75cc4deb2667&=&format=webp&quality=lossless&width=820&height=671)

2. Change computer name:
   ![Change computer name](https://media.discordapp.net/attachments/1295155312151625748/1295165229352878110/image.png?ex=6710f3dd&is=670fa25d&hm=b07902a342f7d4614dbc5d1821013f27a5bb1dad2c05b3123f93599d6e5596cc&=&format=webp&quality=lossless&width=818&height=671)

3. Install Active Directory Domain Services:
   ![Install Active Directory Domain Services](https://media.discordapp.net/attachments/1295155312151625748/1295166707895107674/image.png?ex=6710f53e&is=670fa3be&hm=4c1e7b7631f85e7ecff9e228006fd00d00f3991d98ca23947a2d91dffdf22e02&=&format=webp&quality=lossless&width=825&height=671)

4. Deploy a new forest:
   ![Deploy a new forest](https://media.discordapp.net/attachments/1295155312151625748/1295166791776993343/image.png?ex=6710f552&is=670fa3d2&hm=c5f49f167c4fa841527aece14e02e5a58f865ad5f398c7034fcfca609c8f48ab&=&format=webp&quality=lossless&width=821&height=671)

5. Enable Recycle Bin:
   ![Enable Recycle Bin](https://media.discordapp.net/attachments/1295155312151625748/1295172454397902882/image.png?ex=6710fa98&is=670fa918&hm=03e20a2cd68ab9d74ce3893656b7ca78ccd5cbaaa1608203a49868e75fada340&=&format=webp&quality=lossless&width=822&height=671)

6. Setup static IP for server:
   ![Setup static IP for server](https://media.discordapp.net/attachments/1295155312151625748/1295463187969474663/image.png?ex=6711609c&is=67100f1c&hm=90d82b60302b9a9815e6c4861089c4afa669972ee709872427e293acf26e6c6e&=&format=webp&quality=lossless&width=823&height=671)

### Setting up Desktop1 / helpdesk

1. Copy Administrator user for new user "helpdesk":
   ![Copy Administrator user](https://media.discordapp.net/attachments/1295155312151625748/1295172858519224421/image.png?ex=6710faf8&is=670fa978&hm=fed81311117c258be7d1c1f55929e70b30017b8c53e511de978b83475e450617&=&format=webp&quality=lossless&width=820&height=671)

2. Install Windows 10 Pro:
   ![Install Windows 10 Pro](https://media.discordapp.net/attachments/1295155312151625748/1295462100076072970/image.png?ex=67115f99&is=67100e19&hm=0b7bf81a8e22daf897d14f40f1fd30f5b5ff5007f08b56404d67c43a936aaee5&=&format=webp&quality=lossless&width=822&height=671)

## Notes

[Add any additional notes, challenges faced, or lessons learned during the setup]

