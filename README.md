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
  - [Organizational Unit / Group Policies](#organizational-unit--group-policies)
  - [File Share](#file-share)
  - [Remote Desktop](#remote-desktop)
  - [PDQ Deploy / Inventory](#pdq-deploy--inventory)
  - [Printer Setup](#printer-setup)
  - [Spiceworks](#spiceworks)
  - [Delegate Control / Account Locked Out](#delegate-control--account-locked-out)
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
4. Configured domain settings, TCP/IP, file sharing, and network printing services.
5. Created and linked group policy objects in Active Directory
6. Set up PDQ Deploy for automated software deployment and PDQ Inventory for comprehensive asset management.
7. Implemented security measures such as Delegate Control and account lockout policies.

## Program Walk-through

### Windows Server 2016 / Active Directory Installation

1. Install Windows Server 2016: <br />
   ![Install Windows Server 2016](https://media.discordapp.net/attachments/1295155312151625748/1295155496633897090/image.png?ex=6710eacd&is=670f994d&hm=73f21d19f9176705ec4b78a6d5764cfb3486f918b2c747b8083d75cc4deb2667&=&format=webp&quality=lossless&width=820&height=671)

2. Change computer name: <br />
   ![Change computer name](https://media.discordapp.net/attachments/1295155312151625748/1295165229352878110/image.png?ex=6710f3dd&is=670fa25d&hm=b07902a342f7d4614dbc5d1821013f27a5bb1dad2c05b3123f93599d6e5596cc&=&format=webp&quality=lossless&width=818&height=671)

3. Install Active Directory Domain Services: <br />
   ![Install Active Directory Domain Services](https://media.discordapp.net/attachments/1295155312151625748/1295166707895107674/image.png?ex=6710f53e&is=670fa3be&hm=4c1e7b7631f85e7ecff9e228006fd00d00f3991d98ca23947a2d91dffdf22e02&=&format=webp&quality=lossless&width=825&height=671)

4. Deploy a new forest: <br />
   ![Deploy a new forest](https://media.discordapp.net/attachments/1295155312151625748/1295166791776993343/image.png?ex=6710f552&is=670fa3d2&hm=c5f49f167c4fa841527aece14e02e5a58f865ad5f398c7034fcfca609c8f48ab&=&format=webp&quality=lossless&width=821&height=671)

5. Enable Recycle Bin: <br />
   ![Enable Recycle Bin](https://media.discordapp.net/attachments/1295155312151625748/1295172454397902882/image.png?ex=6710fa98&is=670fa918&hm=03e20a2cd68ab9d74ce3893656b7ca78ccd5cbaaa1608203a49868e75fada340&=&format=webp&quality=lossless&width=822&height=671)

6. Setup static IP for server: <br />
   ![Setup static IP for server](https://media.discordapp.net/attachments/1295155312151625748/1295463187969474663/image.png?ex=6711609c&is=67100f1c&hm=90d82b60302b9a9815e6c4861089c4afa669972ee709872427e293acf26e6c6e&=&format=webp&quality=lossless&width=823&height=671)
   
7. Change VM network settings: <br />
   ![Change VM network settings](https://media.discordapp.net/attachments/1295155312151625748/1295463491292893265/image.png?ex=671160e4&is=67100f64&hm=2c1dd7616e4ca406786e6a5ff5c18f1d351d5ce532cc181de4a51b3cfedd4f30&=&format=webp&quality=lossless&width=822&height=671)

### Setting up Desktop1 / helpdesk

1. Copy Administrator user for new user "helpdesk": <br />
   ![Copy Administrator user](https://media.discordapp.net/attachments/1295155312151625748/1295172858519224421/image.png?ex=6710faf8&is=670fa978&hm=fed81311117c258be7d1c1f55929e70b30017b8c53e511de978b83475e450617&=&format=webp&quality=lossless&width=820&height=671)

2. Install Windows 10 Pro: <br />
   ![Install Windows 10 Pro](https://media.discordapp.net/attachments/1295155312151625748/1295462100076072970/image.png?ex=67115f99&is=67100e19&hm=0b7bf81a8e22daf897d14f40f1fd30f5b5ff5007f08b56404d67c43a936aaee5&=&format=webp&quality=lossless&width=822&height=671)
   
3. Enable Administrator account and delete the User account: <br />
   ![Enable Administrator account and delete the User account](https://media.discordapp.net/attachments/1295155312151625748/1295471649671483485/image.png?ex=6711687d&is=671016fd&hm=eab55b85c7ab950833065227e1f8cb625618a621d62656bb8c060848f591fc6d&=&format=webp&quality=lossless&width=820&height=671)
   
4. Install RSAT tools: Open Settings > System > Optional Features > Add a feature <br />
   ![Install RSAT tools](https://media.discordapp.net/attachments/1295155312151625748/1295475573044285442/image.png?ex=67116c25&is=67101aa5&hm=9019e31d29e09429fbdc40192ce88b79f7af1ffc83a0aadf0e676c6d72d8a6fa&=&format=webp&quality=lossless&width=821&height=671)
   
5. Setup static ip and VM network settings <br />
   ![Setup static ip and VM network settings](https://media.discordapp.net/attachments/1295155312151625748/1295478494767218738/image.png?ex=67116edd&is=67101d5d&hm=1d1b55d443521f1cfa217782781ebd70ac7088440a38217f62e7a6eb0419a08a&=&format=webp&quality=lossless&width=821&height=671)
   
6. Change computer name and join domain <br />
   ![Change computer name and join domain](https://media.discordapp.net/attachments/1295155312151625748/1295479935422562324/image.png?ex=67117035&is=67101eb5&hm=f308e2df7314ddc5d792ba2c3217cece5aea96bfce008ef5fc8ab581e83001da&=&format=webp&quality=lossless&width=822&height=671)
   
7. Log into domain <br />
   ![Log into domain](https://media.discordapp.net/attachments/1295155312151625748/1295480227878670409/image.png?ex=6711707b&is=67101efb&hm=85c06dd45f7893ca721c11b85d53e6c27e0025ac370eca21c055bb3d4983568d&=&format=webp&quality=lossless&width=820&height=671)
   
6. Verify computer is in domain <br />
   ![Verify computer is in domain](https://media.discordapp.net/attachments/1295155312151625748/1295480583480279101/image.png?ex=671170cf&is=67101f4f&hm=78828daa6af216e45409beedd0782590c5ef8456891cd62c50cc7d7dacacba8e&=&format=webp&quality=lossless&width=820&height=671)

### Organizational Unit / Group Policies

1. Create HR OU: <br />
   ![Create HR OU](https://media.discordapp.net/attachments/1295155312151625748/1295484350783033445/image.png?ex=67117452&is=671022d2&hm=0cb441f587ba24f43767a401f8544772e6381b3706e56ace8ce8eaff844bbf42&=&format=webp&quality=lossless&width=823&height=671)
   
2. Create vchim user: <br />
   ![Create vchim user](https://media.discordapp.net/attachments/1295155312151625748/1295484552336244768/image.png?ex=67117482&is=67102302&hm=d7c8bb53d3b7f888dc14c615d882b353f25cba0c1f6d06aa716f74a861572d94&=&format=webp&quality=lossless&width=820&height=671)
   
3. Move vchim to HR: <br />
   ![Move vchim to HR](https://media.discordapp.net/attachments/1295155312151625748/1295484764983132160/image.png?ex=671174b4&is=67102334&hm=77e6426fb79a4bfe3b4d1760ca0f0d7d1e2ac20b030fbcf0c49a4b2099d19501&=&format=webp&quality=lossless&width=818&height=671)
   
4. Create IT OU: <br />
   ![Create IT OU](https://media.discordapp.net/attachments/1295155312151625748/1295484853281755196/image.png?ex=671174c9&is=67102349&hm=e5b2d69ce16594f5aa4b5148c78664e05893ccea19616d71a20a01672ac58889&=&format=webp&quality=lossless&width=818&height=671)
   
5. Move helpdesk to IT: <br />
   ![Move helpdesk to IT](https://media.discordapp.net/attachments/1295155312151625748/1295484942104395877/image.png?ex=671174df&is=6710235f&hm=44879f2bcc1ccc1564654716b594bcd2f7a750438d47ed107fc57db1492cb2fe&=&format=webp&quality=lossless&width=816&height=671)
   
6. Add Account Lockout policy to Default Domain Policy: Computer Configuration > Policies > Windows Settings > Security Settings > Account Policies > Account Lockout <br />
   ![Add Account Lockout policy to Default Domain Policy](https://media.discordapp.net/attachments/1295155312151625748/1295499848661078026/image.png?ex=6710da01&is=670f8881&hm=68a0fec47f1dd309cc036eca25592bddafefb7db28124d8585c2dca4ef9dd7e6&=&format=webp&quality=lossless&width=823&height=671)
   
7. Change maximum password age properties: Computer Configuration > Policies > Windows Settings > Security Settings > Account Policies > Password Policy <br />
   ![Change maximum password age properties](https://media.discordapp.net/attachments/1295155312151625748/1295500005037314201/image.png?ex=6710da26&is=670f88a6&hm=dde55f031d64fe92fac3f7fe9be6be290e9028900cd51efbdc065214fa11d925&=&format=webp&quality=lossless&width=822&height=671)

8. Replicate VM setup for Desktop 2 and log in to vchim: <br />
   ![Replicate VM setup for Desktop 2](https://media.discordapp.net/attachments/1295155312151625748/1295508069618286703/image.png?ex=6710e1a9&is=670f9029&hm=49ec46a79ad9f5bd4e810ad6fd25ce5a3a9f0638ab43e83e2a7ec7ff79d87f7c&=&format=webp&quality=lossless&width=821&height=671)

9. Task Manager Policy: <br />
   ![Task Manager Policy](https://media.discordapp.net/attachments/1295155312151625748/1295860616153661480/image.png?ex=6710d87e&is=670f86fe&hm=b0c0a5d10d4206442ae5b9774aa5ddecebaf0e3b86a74fd9165434c553c30c51&=&format=webp&quality=lossless&width=825&height=671)
   
10. Add vchim to users <br />
   ![Add vchim to users](https://media.discordapp.net/attachments/1295155312151625748/1295861037362581524/image.png?ex=6710d8e3&is=670f8763&hm=f0be4418a94397e1caf325cd1d4cb8b15f98813a6755d20658dc557c068c677f&=&format=webp&quality=lossless&width=827&height=671)

   
11. User Configuration > Policies > Administrative Template > System > Ctrl + Alt + Del Options: <br />
   ![Add vchim to users](https://media.discordapp.net/attachments/1295155312151625748/1295861977238863943/image.png?ex=6710d9c3&is=670f8843&hm=3c69e8ab19496d407d9f4079b1abfe35da627376aedb086c4aa7a091b548e910&=&format=webp&quality=lossless&width=820&height=671)

   
12. Move policy to HR and enforce <br />
   ![Move policy to HR and enforce](https://media.discordapp.net/attachments/1295155312151625748/1295862174505504829/image.png?ex=6710d9f2&is=670f8872&hm=0cbbf546878ce9353c0b9e7485d3d8ecf6d678547fa2b339ee46f531ac2d5642&=&format=webp&quality=lossless&width=821&height=671)
   
13. Test policy: gpupdate /force <br />
   ![Test policy](https://media.discordapp.net/attachments/1295155312151625748/1295863515617431593/image.png?ex=6710db32&is=670f89b2&hm=f66ece7efaccad05b6780e77cfbe39295f4c01514b72e25747d64aef3eefd66a&=&format=webp&quality=lossless&width=818&height=671)
   
### File Share

1. Create HR Share and Personal Share: <br />
   ![Create HR Share and Personal Share](https://media.discordapp.net/attachments/1295155312151625748/1295511888192340108/image.png?ex=6710e537&is=670f93b7&hm=3d6e11d5911bd6a878cd27f3491c18b7edd79550270980200be305acaba807ba&=&format=webp&quality=lossless&width=821&height=671)
   
2. Create HR Security Group: <br />
   ![Create HR Security Group](https://media.discordapp.net/attachments/1295155312151625748/1295512688562143323/image.png?ex=6710e5f6&is=670f9476&hm=1d2436104b6e2ec1fc15fbe71db989ed520fade95c1b9e2286dbd6424d0884c2&=&format=webp&quality=lossless&width=820&height=671)
   
3. Add helpdesk to managed by: <br />
   ![Add helpdesk to managed by](https://media.discordapp.net/attachments/1295155312151625748/1295513063704891502/image.png?ex=6710e64f&is=670f94cf&hm=413de668d42adada925c4b6a10241e557e2360a45e6000b6bda64031e5498d7f&=&format=webp&quality=lossless&width=821&height=671)
   
4. Do the same for Personal: <br />
   ![Do the same for Personal](https://media.discordapp.net/attachments/1295155312151625748/1295513341376200846/image.png?ex=6710e692&is=670f9512&hm=daa8c7fca878f56ac796480e6f4b92469c60559d7b5bccf551b87fcae5f49bab&=&format=webp&quality=lossless&width=820&height=671)
   
5. Add vchim as a member to both #HR and #Personal: <br />
   ![Add vchim as a member to both #HR and #Personal](https://media.discordapp.net/attachments/1295155312151625748/1295514053590126593/image.png?ex=6710e73b&is=670f95bb&hm=8946e6b6c511aba02ce4895d67a7dd023961a81905672a49fb2e18f1daceff7f&=&format=webp&quality=lossless&width=821&height=671)

6. Disable inheritance, remove users, add helpdesk and #Personal: <br />
   ![Disable inheritance, remove users, add helpdesk and #Personal](https://media.discordapp.net/attachments/1295155312151625748/1295515217727455283/image.png?ex=6710e851&is=670f96d1&hm=30ca90e88ecaa88f64c28efb4be92ace2ee93ba3f50d7de077725f6a819dee25&=&format=webp&quality=lossless&width=823&height=671)

7. Share the folder with Read/Write: <br />
   ![Share the folder with Read/Write](https://media.discordapp.net/attachments/1295155312151625748/1295515543826075680/image.png?ex=6710e89f&is=670f971f&hm=f7fc7989881d3408184e98e28ebbdcaaec4d7b9a73d0ddf68dbfc45b5e43124c&=&format=webp&quality=lossless&width=821&height=671)
   
8. Repeat for HR: <br />
   ![Repeat for HR](https://media.discordapp.net/attachments/1295155312151625748/1295516318086332499/image.png?ex=6710e957&is=670f97d7&hm=8e98ab0fbda996763d67265a4be88bd0e80900f528237ad78404c4a5a3902102&=&format=webp&quality=lossless&width=818&height=671)
   
9. Map drives on user computer : <br />
   ![Map drives on user computer](https://media.discordapp.net/attachments/1295155312151625748/1295517199947141150/image.png?ex=6710ea2a&is=670f98aa&hm=669b7db3f584a012662b616cc30a4b43ba563e644a7739ea310e673b6cdf886f&=&format=webp&quality=lossless&width=817&height=671)
   
10. Confirm mapped drives: <br />
   ![Confirm mapped drives](https://media.discordapp.net/attachments/1295155312151625748/1295518348909482074/image.png?ex=6710eb3b&is=670f99bb&hm=ad68ce85df30b58805812194163652cf57770770393153bc1ee32c8caeb3f428&=&format=webp&quality=lossless&width=822&height=671)
   
11. Map drives through Active Directory: <br />
   ![Map drives through Active Directory](https://media.discordapp.net/attachments/1295155312151625748/1295518846911778907/image.png?ex=6710ebb2&is=670f9a32&hm=3c7a4b9152630a5086bfdedc3204b5bfebd531e06370e05d26d30ff651fb3b1e&=&format=webp&quality=lossless&width=823&height=671)
   
12. Confirm mapped drives: <br />
   ![Confirm mapped drives](https://media.discordapp.net/attachments/1295155312151625748/1295519838235660328/image.png?ex=6710ec9f&is=670f9b1f&hm=190ea7d33ebe6999147db1333e75edba54a48b1fa0c569450b24ccfd1284a34a&=&format=webp&quality=lossless&width=821&height=671)

### Remote Desktop

1. Enable remote desktop on user computer: <br />
   ![Enable remote desktop on user computer](https://media.discordapp.net/attachments/1295155312151625748/1295843605797277817/image.png?ex=67117167&is=67101fe7&hm=a06ca318a523c9abdafb0886a8975eb1095c74eed3e4de4d448e1c1c9f3975d0&=&format=webp&quality=lossless&width=822&height=671)
   
2. Remote desktop from helpdesk/Desktop1 to Desktop2: <br />
   ![Remote desktop from helpdesk/Desktop1 to Desktop2](https://media.discordapp.net/attachments/1295155312151625748/1295844351167037470/image.png?ex=67117218&is=67102098&hm=7f721e8ab8e9b7932863788ed75026a39622cbd33e2b669cdca7f1d5b2196471&=&format=webp&quality=lossless&width=810&height=671)
   
3. Example Use: Create new folders <br />
   ![Example Use](https://media.discordapp.net/attachments/1295155312151625748/1295847144342945894/image.png?ex=671174b2&is=67102332&hm=ce665051110cce8c7b4c042366b4caa0b67a0a74febc8dc37ecd1c0837d5d1db&=&format=webp&quality=lossless&width=807&height=671)
   
4. Enable Remote Registry on both computers: Way to remote in without bugging user <br />
   ![Enable Remote Registry on both computers](https://media.discordapp.net/attachments/1295155312151625748/1295849162843095164/image.png?ex=67117694&is=67102514&hm=a9373498124da8bb0bfb59228f3288f8a5b42c9ee42569e727e7940b652f864f&=&format=webp&quality=lossless&width=823&height=671)
   
5. Allow port 445 for Remote Registry: Windows Defender Firewall > Inbound Rule > New Rule > Port:445 <br />
   ![Allow port 445 for Remote Registry](https://media.discordapp.net/attachments/1295155312151625748/1295851477197389896/image.png?ex=671178bb&is=6710273b&hm=71a9cb644c1c1278f44d5f3a62ad5950106e8ada3f40a28bb6aeb0b34e4a25f8&=&format=webp&quality=lossless&width=820&height=671)
   
6. Select Desktop2 in Registry Editor on Desktop1 <br />
   ![Select Desktop2 in Registry Editor on Desktop1](https://media.discordapp.net/attachments/1295155312151625748/1295849502854610984/image.png?ex=671176e5&is=67102565&hm=d6df27018482d4019a79c0b23a99477f08168d2aa6d77ca614aa3962b75651fb&=&format=webp&quality=lossless&width=806&height=671)
   
7. Determine share drives: <br />
   ![Determine share drives](https://media.discordapp.net/attachments/1295155312151625748/1295852349889445898/image.png?ex=6711798b&is=6710280b&hm=0533160d93f5c11b753d1dbd3c9277ae17f37b98e9c5e40b0da913a426b798c0&=&format=webp&quality=lossless&width=806&height=671)
   
8. Use c$ to access folders: \\desktop2\c$ <br />
   ![Use c$ to access folders](https://media.discordapp.net/attachments/1295155312151625748/1295852582492704778/image.png?ex=671179c3&is=67102843&hm=5f20e4a3d99578c9a06850f77125f46e3fe082d9c0e4cb9b0e7828dd7bda3698&=&format=webp&quality=lossless&width=807&height=671)
   
9. Invite through file: Windows Remote Assistance <br />
   ![Windows Remote Assistance](https://media.discordapp.net/attachments/1295155312151625748/1295853512160444467/image.png?ex=6710d1e1&is=670f8061&hm=3d1b78449a23820a6904816f1191c6ebe21dcfe12a6d167bc7b737c6600075c2&=&format=webp&quality=lossless&width=820&height=671)
   
10. Use c$ to access the invitation file: <br />
   ![Use c$ to access the invitation file](https://media.discordapp.net/attachments/1295155312151625748/1295854288152694845/image.png?ex=6710d29a&is=670f811a&hm=ad212dc3ee39e2f2fdf8ea03aafd3111380fc577dae6bb73a0668425f860bbb9&=&format=webp&quality=lossless&width=810&height=671)
   
11. Windows Remote Assistance: <br />
   ![Windows Remote Assistance](https://media.discordapp.net/attachments/1295155312151625748/1295855171955331175/image.png?ex=6710d36c&is=670f81ec&hm=5b7eb5a3cf303c52f769fc28ef5a8c7af0e380c6a05606948bf9749546034d62&=&format=webp&quality=lossless&width=1440&height=647)
   
### PDQ Deploy / Inventory

1. Install Virtualbox Guest Additions: <br />
   ![Install Virtualbox Guest Additions](https://media.discordapp.net/attachments/1295155312151625748/1295867221129695322/image.png?ex=6710dea5&is=670f8d25&hm=67c93240a2410296b7553661b2135e599f083d91e36f5bc08d99f0fb8e1b2bbc&=&format=webp&quality=lossless&width=820&height=671)
   
2. Link shared folder: <br />
   ![Link shared folder](https://media.discordapp.net/attachments/1295155312151625748/1295868138893742090/image.png?ex=6710df80&is=670f8e00&hm=ca110a8844646219b1ee0ec70f373a40b082865d8f6b1790958c52c9bc2a8d79&=&format=webp&quality=lossless&width=821&height=671)
   
3. Grab PDQ from the shared folder: <br />
   ![Grab PDQ from the shared folder](https://media.discordapp.net/attachments/1295155312151625748/1295868297249820684/image.png?ex=6710dfa6&is=670f8e26&hm=cb0b154f1f62f3e578299bde63f56460a7e6406811cce5b2b1222171e0a20838&=&format=webp&quality=lossless&width=818&height=671)
   
4. Reset network settings to internet access:  <br />
   ![Reset network settings to internet access](https://media.discordapp.net/attachments/1295155312151625748/1295868867939401790/image.png?ex=6710e02e&is=670f8eae&hm=1cff3391e44b5a3bbcf87d18cf4b06765868d0cd6373336950599c30b812c9c4&=&format=webp&quality=lossless&width=818&height=671)
   
5. Install .NET Framework: Requires internet *Make sure to revert the netowrk settings <br />
   ![Install .NET Framework](https://media.discordapp.net/attachments/1295155312151625748/1295869124798316574/image.png?ex=6710e06b&is=670f8eeb&hm=b3417986304daa378bef33e398ec7f091ccc13b74fac5ea6a7f2a6941468747f&=&format=webp&quality=lossless&width=820&height=671)
   
6. Install PDQ Deploy: <br />
   ![Install PDQ Deploy](https://media.discordapp.net/attachments/1295155312151625748/1295870051739631686/image.png?ex=6710e148&is=670f8fc8&hm=1de50156fdb00d308011adba92377b0bbfdea9b3424f4c0a9616c24e22764bb3&=&format=webp&quality=lossless&width=820&height=671)
   
7. Download Firefox package and deploy: Deploy Once > Choose Target > Active Directory > Computers > SERVER2016 <br />
   ![Download Firefox package and deploy](https://media.discordapp.net/attachments/1295155312151625748/1295870051739631686/image.png?ex=6710e148&is=670f8fc8&hm=1de50156fdb00d308011adba92377b0bbfdea9b3424f4c0a9616c24e22764bb3&=&format=webp&quality=lossless&width=820&height=671)
   
8. Confirm deployment: <br />
   ![Confirm deployment](https://media.discordapp.net/attachments/1295155312151625748/1295877058408484924/image.png?ex=6710e7ce&is=670f964e&hm=17c520b1b72b26dd47041a28525c2f404901e6132697e47db4c80145276d9074&=&format=webp&quality=lossless&width=821&height=671)
 
9. Install PDQ Inventory: <br />
   ![Install PDQ Inventory](https://media.discordapp.net/attachments/1295155312151625748/1295880901103976478/image.png?ex=6710eb63&is=670f99e3&hm=a4fac77c41552def21157a030dbdae30e6f769da7fda25e023d101ab12f26990&=&format=webp&quality=lossless&width=821&height=671)
 
10. Add desktop2 to PDQ Inventory: <br />
   ![Add desktop2 to PDQ Inventory](https://media.discordapp.net/attachments/1295155312151625748/1295883111560642611/image.png?ex=6710ed72&is=670f9bf2&hm=ac3c476050dad6f8eb636f488ac93c77ce8276975e3b9bf551cd124796c0dd93&=&format=webp&quality=lossless&width=818&height=671)
 
11. Example Use: Run report on shared folders <br />
   ![Example Use](https://media.discordapp.net/attachments/1295155312151625748/1295883717213945929/image.png?ex=6710ee02&is=670f9c82&hm=9336beb2573128995c8e07cb302734c85709168614fe4d8ead6d8b28fe7b7018&=&format=webp&quality=lossless&width=823&height=671)
 
12. Example Use: Check computer system information <br />
   ![Example Use](https://media.discordapp.net/attachments/1295155312151625748/1295883797513900052/image.png?ex=6710ee15&is=670f9c95&hm=81c7b9d901145c333bef978ff043bce27e78dab017f1e104074a4c3b8ff7f59f&=&format=webp&quality=lossless&width=818&height=671)
 
13. Example Use: Check installed applications <br />
   ![Example Use](https://media.discordapp.net/attachments/1295155312151625748/1295883852249694230/image.png?ex=6710ee22&is=670f9ca2&hm=d4a01d5a3e2e0b337f9f2c244457fd904ff6835afa2b3784779cf182bed32608&=&format=webp&quality=lossless&width=823&height=671)
 
### Printer Setup

1. Install Printer Server: <br />
   ![Install Printer Server](https://media.discordapp.net/attachments/1295155312151625748/1295885525411958784/image.png?ex=6710efb1&is=670f9e31&hm=315c599953267923a11297f479cb9ae3277214654ebdb74141adb341c9343bbb&=&format=webp&quality=lossless&width=817&height=671)
   
2. Add new printer: <br />
   ![Add new printer](https://media.discordapp.net/attachments/1295155312151625748/1295887306779267212/image.png?ex=6710f15a&is=670f9fda&hm=a349840b5c58e5aa2d4671ecc12ae67e6a6d2b3ae1664ff6c09c705b1c2c5229&=&format=webp&quality=lossless&width=825&height=671)
   
3. Add printer using existing port: <br />
   ![Add printer using existing port](https://media.discordapp.net/attachments/1295155312151625748/1295887307001299006/image.png?ex=6710f15a&is=670f9fda&hm=5f9288e29df0ac68ca2a7ce4f8fb8c98812a11f2aedf6ba1cae6ebe4408d31cf&=&format=webp&quality=lossless&width=821&height=671)
   
4. Install HP printer: <br />
   ![Install HP printer](https://media.discordapp.net/attachments/1295155312151625748/1295887307211018331/image.png?ex=6710f15a&is=670f9fda&hm=0275694a9192bf60f4a50579b00e9f1f1ef3a92aa162c4aceffb26bbf909f23e&=&format=webp&quality=lossless&width=823&height=671)
   
5. Share printer: <br />
   ![Share printer](https://media.discordapp.net/attachments/1295155312151625748/1295887320096051240/image.png?ex=6710f15d&is=670f9fdd&hm=cdaa8e64a6e3c45298560cad8cd90ca3983a1c2dcd79f78105917f3381520812&=&format=webp&quality=lossless&width=821&height=671)
   
6. Add #HR group to printer: <br />
   ![Add #HR group to printer](https://media.discordapp.net/attachments/1295155312151625748/1295887508680478720/image.png?ex=6710f18a&is=670fa00a&hm=fc6affaaf65c083f91736e228660e558c30d07772f032776955cdafa0c6cc1a7&=&format=webp&quality=lossless&width=822&height=671)
   
7. Search for printer on desktop2: <br />
   ![Search for printer on desktop2](https://media.discordapp.net/attachments/1295155312151625748/1295888071333773353/image.png?ex=6710f210&is=670fa090&hm=0d0d330a23f8daddf69566f538219c8dadf1c7b7750c7a8e1144ddf1cf59f695&=&format=webp&quality=lossless&width=823&height=671)

8. Confirm shared printer: <br />
  ![Confirm shared printer](https://media.discordapp.net/attachments/1295155312151625748/1295888195392634940/image.png?ex=6710f22e&is=670fa0ae&hm=b259fc70c2fd676475b0d8ab584281b8d0c9cc6210c5a3a279ddd774d6bdd058&=&format=webp&quality=lossless&width=817&height=671)
   
### Spiceworks

1. Create a remote session: <br />
  ![Create a remote session](https://media.discordapp.net/attachments/1295155312151625748/1295891703118696508/image.png?ex=6710f572&is=670fa3f2&hm=ed2c4ab726f42af5e44dc6f5e04225455cb85ca1aa04e671608b7f48956a45bb&=&format=webp&quality=lossless&width=1406&height=671)
   
2. Join remote session: *Change network settings to allow internet access <br />
  ![Create a remote session](https://media.discordapp.net/attachments/1295155312151625748/1295892213598781533/image.png?ex=6710f5ec&is=670fa46c&hm=4c39a684a22d1fcee9abb3b517615ea444d5dca3dc0061c306678b305d4a17cf&=&format=webp&quality=lossless&width=823&height=671)

   
3. Download and install application to use remote help: <br />
  ![Download and install application to use remote help](https://media.discordapp.net/attachments/1295155312151625748/1295893310858199060/image.png?ex=6710f6f1&is=670fa571&hm=90dae9051cac18abd22625e18d0c83b127269939d1d4c6a3980b586e7a2367f7&=&format=webp&quality=lossless&width=1393&height=671)

### Delegate Control / Account Locked Out
      
1. Create new OU and User: <br />
  ![Create new OU and User](https://media.discordapp.net/attachments/1295155312151625748/1295896695401480272/image.png?ex=6710fa18&is=670fa898&hm=c15d58fc8f25f725dba6a60df1ab17250cc0ccc2071a7b39c0999f3a11859701&=&format=webp&quality=lossless&width=822&height=671)
      
2. Delegate control for password resets: <br />
  ![Delegate control for password resets](https://media.discordapp.net/attachments/1295155312151625748/1295896995583492137/image.png?ex=6710fa60&is=670fa8e0&hm=13e7e5da9823dd2c6d76644896433771a8636aef7a7489860def74d176a342e5&=&format=webp&quality=lossless&width=820&height=671)
      
3. Login to jdoe: <br />
  ![Login to jdoe](https://media.discordapp.net/attachments/1295155312151625748/1295897232696016978/image.png?ex=6710fa98&is=670fa918&hm=1ee7120cdba505c9b163250a2d666d231b29ab37c9c104f0d4fd2da1dfbc4631&=&format=webp&quality=lossless&width=822&height=671)

4. Verify account permissions: <br />
  ![Verify account permissions](https://media.discordapp.net/attachments/1295155312151625748/1295897968322416670/image.png?ex=6710fb48&is=670fa9c8&hm=d5170cd21badb896edebf35d7d9fc5e694ab4d453c3b3bc2010a6051296aa7be&=&format=webp&quality=lossless&width=825&height=671)

5. Install ALTools: <br />
  ![Install ALTools](https://media.discordapp.net/attachments/1295155312151625748/1295898520628367422/image.png?ex=6710fbcb&is=670faa4b&hm=b47a341d5c355bbfe73ccbcf62bad7c00efa9f12dc46a7011b16faa9c5176c0c&=&format=webp&quality=lossless&width=823&height=671)

6. Get locked out of jdoe: <br />
  ![Get locked out of jdoe](https://media.discordapp.net/attachments/1295155312151625748/1295898620079640577/image.png?ex=6710fbe3&is=670faa63&hm=3205c0b976e16b0e9f090f8e424a7cf2ab3705157294b1d9e1351c1f1d91e0eb&=&format=webp&quality=lossless&width=815&height=671)

7. Launch lockout status: Select target jdoe <br />
  ![Launch lockout status](https://media.discordapp.net/attachments/1295155312151625748/1295898917426430053/image.png?ex=6710fc2a&is=670faaaa&hm=be9f76628bd0455e6ad7a2bdd5886a5deda7fe4b1a86e02d82a0034aac651acf&=&format=webp&quality=lossless&width=823&height=671)

8. View information on passwords and lockout <br />
  ![View information on passwords and lockout](https://media.discordapp.net/attachments/1295155312151625748/1295899089636167721/image.png?ex=6710fc53&is=670faad3&hm=c51ee319fc7db42aeb48db97083a406648950bc18c3146680b83ee07c06abce3&=&format=webp&quality=lossless&width=818&height=671)

9. Unlock account <br />
  ![Unlock account](https://media.discordapp.net/attachments/1295155312151625748/1295899325859368960/image.png?ex=6710fc8b&is=670fab0b&hm=cccd6c3d0df9c5ed8b2dc81b298f20fc684e4f041cb7f6c9a99a1b7b32ea894e&=&format=webp&quality=lossless&width=823&height=671)

## Notes
CMD Commands
ipconfig - /all
net use - displays shared drives
net user hepdesk /domain - displays group memberships, password information for user "helpdesk"
ping - -t

