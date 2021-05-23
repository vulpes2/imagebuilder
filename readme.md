IMPORTANT: the branches have been renamed - the old master branch is now called legacy, the old dev branch dev-old and the old experimental branch is now the main branch

# introduction

this is a simple framework for building bootable sd card images for various (currently arm based) small computer like devices. it is supposed to run natively, i.e. if you want to build an image for a 32bit arm system you should run it on a 32bit arm system and so on. i started it when i wanted to easily and reproducably build bootable sd card images for some arm devices for which there are no such images with recent distributions and linux kernels available or do not exist at all. i'm aware of the armbian (https://www.armbian.com/) framework, which has a similar goal and is much more advanced, but i wanted something simpler so that i can easier adjust it for prototyping and i wanted to build everything natively as i do not really have any strong intel machine for cross compiling. if anyone with amrbian knowledge and a proper build environment is interested to port over the patches etc. for the few systems not yet supported by armbian to it, that would be more than welcome.

please keep in mind that the intention of those images is to make it easier to get started on not too well supported systems or setups. they are not intended as a fully end user ready distribution - some fine tuning and adjustment will most probably be required still to make them fully working, but at least you do not have to think about how to get this device booting or where to get a working kernel from etc. ...

# creating images

see scripts/readme.md as a start

more coming soon ...

# using the images

simply write/flash (not just copy!) the images to an sd card - there is a lot of documentation about how to do this on the web. the images require an sd card of at least 8gb size (for the newer images even 4gb sould be enough) - more is no problem and can be made useable after the first boot of the image.

the images provided are ubuntu 20.04 lts (focal) with the xubuntu desktop environment. debian 11 (bullhead) with the xfce desktop environment will be added as soon as it gets officially released. they have a user named "linux" configured with the password "changeme" and sudo permission (use "sudo -i" to get root). the hostname is set to "changeme". they are assuming a us keyboard and are setup for english, so one should configure it as needed after the first boot - a good start might be:

* locale: dpkg-reconfigure locales
* timezone: dpkg-reconfigure tzdata
* console keyboard (run this on the console if needed at all): dpkg-reconfigure keyboard-configuration
* console (run this on the console if needed at all): dpkg-reconfigure console-setup

or even simpler, just use the various graphical settings tools installed.

some commands to set the keyboardmapping in an x terminal:

* english: setxkbmap us
* french: setxkbmap fr
* german: setxkbmap de
* italian: setxkbmap it
* portuguese: setxkbmap pt
* russian: setxkbmap ru
* spanish: setxkbmap es
* ...
* onscreen keyboard: apt-get install matchbox-keyboard ; matchbox-keyboard
      alternatively: apt-get install onboard ; onboard
* for console: loadkeys us (etc. like above)

to use all the space on your sd card, please run the following script as root after the first boot: "/scripts/extend-rootfs.sh"

more coming soon ...

# system specific information

- allwinner h3: https://github.com/hexdump0815/imagebuilder/blob/main/systems/allwinner_h3/readme.md
- allwinner h6: https://github.com/hexdump0815/imagebuilder/tree/main/systems/allwinner_h6#readme
- amlogic gx: https://github.com/hexdump0815/imagebuilder/blob/main/systems/amlogic_gx/readme.md
- amlogic m8:https://github.com/hexdump0815/imagebuilder/blob/main/systems/amlogic_m8/readme.md
- chromebook kukui: https://github.com/hexdump0815/imagebuilder/blob/main/systems/chromebook_kukui/readme.md
- chromebook nyan: https://github.com/hexdump0815/imagebuilder/blob/main/systems/chromebook_nyan/readme.md
- chromebook oak: https://github.com/hexdump0815/imagebuilder/blob/main/systems/chromebook_oak/readme.md
- chromebook peach: https://github.com/hexdump0815/imagebuilder/blob/main/systems/chromebook_peach/readme.md
- chromebook snow: https://github.com/hexdump0815/imagebuilder/blob/main/systems/chromebook_snow/readme.md
- chromebook veyron: https://github.com/hexdump0815/imagebuilder/blob/main/systems/chromebook_veyron/readme.md
- odroid mc1: https://github.com/hexdump0815/imagebuilder/blob/main/systems/odroid_mc1/readme.md
- odroid u3: https://github.com/hexdump0815/imagebuilder/blob/main/systems/odroid_u3/readme.md
- orbsmart s92 and beelink r89: https://github.com/hexdump0815/imagebuilder/blob/main/systems/orbsmart_s92_beelink_r89/readme.md
- raspberry pi 3: https://github.com/hexdump0815/imagebuilder/blob/main/systems/raspberry_pi_3/readme.md
- raspberry pi 4: https://github.com/hexdump0815/imagebuilder/blob/main/systems/raspberry_pi_4/readme.md
- rockchip rk3288: https://github.com/hexdump0815/imagebuilder/blob/main/systems/rockchip_rk3288/readme.md
- rockchip rk33xx: https://github.com/hexdump0815/imagebuilder/blob/main/systems/rockchip_rk33xx/readme.md