# TV BOX , ANDROID BOX , STB PPWN
## All source credited TheFLOW, Stooged, Karo, SiSTRO AND all dev

- THIS IS STABLE VERSION AND Need 50-150 seconds to activate but stable and support some of ps4 region 
- If you need Light version { where is fast , lightweight for minimal linux . you can try it here : 
<a href=https://github.com/zikyu8/tvboxpwn>ZIKYU8 LIGHT [ 30 - 80 Seconds to activate</a> <br>

This is a script to setup <a href=https://github.com/xfangfang/PPPwn_cpp>PPPwn_cpp</a> a c++ rewrite of <a href=https://github.com/TheOfficialFloW/PPPwn>PPPwn</a> on the raspberry pi and run <a href=https://github.com/GoldHEN/GoldHEN>GoldHen</a> on the PS4 fw 11.0, 10.01, 10.00, 9.00<br>
It also supports internet access after pwn and access to ftp, klog and binloader servers launched by goldhen.<br>
A dns blocker is also installed and used to prevent updates.<br>

This repo is focussing on tv box / android box, stb running armbian minimal or server
There is also a webserver to control the pi, change settings and send payloads by accessing http://pppwn.local from the console or your pc if you have internet access enabled.<br> 

<br>

## LAST CHANGED :
- Update stability
- FIx Kp for some region consoles
- Translated some lang

## TESTED STB BOX [ Amlogic chipset ]
[ allwinner , rockchip in future updates maybe ]

- HG860P
- B860H
- X96
- Q96
- T56
- BEELINK


## Install
<br>

You need to install armbian first :

<a href=https://k-space.ee.armbian.com/archive/aml-s9xx-box/archive/Armbian_23.02.2_Aml-s9xx-box_bullseye_current_6.1.11.img.xz>bullseye current</a> <br>
<a href=https://k-space.ee.armbian.com/archive/aml-s9xx-box/archive/Armbian_23.02.2_Aml-s9xx-box_jammy_current_6.1.11.img.xz>Jammy current</a> <br>
<a href=https://k-space.ee.armbian.com/archive/aml-s9xx-box/archive/Armbian_23.11.1_Aml-s9xx-box_bookworm_current_6.1.63.img.xz>Book woorm </a> <br>

Or Download From Ophub Release HEre :
<a href=https://github.com/ophub/amlogic-s9xxx-armbian/releases> DOWNLOAD </a> <br>


Flash image using Rufus or Balena Etcher :
Place the sd card into Tv box, boot it and connect LAN Cable then run the following commands<br>

If you are login using user . use "sudo " command in <br>
If you are login using root , do not use <br>

## CLEAN INSTALL

<br>

```sh
sudo apt update
sudo apt install git -y
git clone https://github.com/zikyu7/linuxpwn2
sudo mkdir /boot/firmware/
cd tvboxpwn
sudo cp -r PPPwn /boot/firmware/
cd /boot/firmware/PPPwn
sudo chmod 777 *
sudo bash install.sh
```

## UPDATE / REINSTALL
[for 6th command ,  dont forget to change zikyu to your username armbian ] , in ex your username is tvbox1 , change this command to ( cd/home/tvbox1 ]
<br>

```sh
sudo rm -f -r tvboxpwn
sudo rm -f -r PI-Pwn
sudo systemctl stop pipwn
cd /boot/firmware/
sudo rm -f -r PPPwn
cd /home/zikyu
git clone https://github.com/zikyu7/tvboxpwn
cd tvboxpwn
sudo cp -r PPPwn /boot/firmware/
cd /boot/firmware/PPPwn
sudo chmod 777 *
bash install.sh
```
<br>

During the install process you will be asked to set some options.<br>

If you are using a <b>usb to ethernet adapter</b> for the connection to the console you need to select yes<br>
If your pi has an ethernet port and you are using a usb to ethernet adapter your interface for the usb adapter should be eth1<br>
If you are using something like a pi zero 2 the interface will be eth0<br>

Once the pi reboots pppwn will run automatically.<br>



## On your PS4:<br>

- Go to `Settings` and then `Network`<br>
- Select `Set Up Internet connection` and choose `Use a LAN Cable`<br>
- Choose `Custom` setup and choose `PPPoE` for `IP Address Settings`<br>
- Enter `ppp` for `PPPoE User ID` and `PPPoE Password`<br>
- NOTE if you enable internet access you must match the username and password entered during the install or use the default `ppp`
- Choose `Automatic` for `DNS Settings` and `MTU Settings`<br>
- Choose `Do Not Use` for `Proxy Server`<br>


For GoldHen you need to place the goldhen.bin file onto the root of a usb drive and plug it into the console.<br>
Once goldhen has been loaded for the first time it will be copied to the consoles internal hdd and the usb is no longer required.<br>
To update goldhen just repeat the above process and the new version will be copied to the internal hdd<br>


==== warning ====

#Fix sudo [ do not use this code ]

```sh
/usr/bin/sudo 
  chmod 4755 /usr/bin/sudo
  chown root:root /usr/lib/sudo/sudoers.so 
  chmod 4755 /usr/lib/sudo/sudoers.so
  chown root:root /etc/sudoers
  chown root:root /etc/sudoers.d /etc/sudoers.d/README  /var/lib/sudo
```
<br>

