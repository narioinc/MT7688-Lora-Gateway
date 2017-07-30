# MT7688-Lora-Gateway
This repo contains the pre built binaries for running your Lora Gateway on MT7688 Based boards like Linkit 7688

# Getting started:
Get a MT7688 based device like the Linkit 7688 or the Onion range of openwrt boards and connect to power. Make sure that the boards are connected to the internet by going through their respective getting started guides.

This guide assumes you have the Linkit board but it shouldnt be any different for other such boards.

MT7688 Linkit gettings started: https://docs.labs.mediatek.com/resource/linkit-smart-7688/en/get-started

# SCP the files to the board
Now open up a scp program like WinSCP for windows or normal scp command in ubuntu/linux and copy the files over to /tmp/ 

Example in Linux/Ubuntu

mkdir lora-gateway
cd lora-gateway
git clone https://github.com/narioinc/MT7688-Lora-Gateway.git
cd MT7688-Lora-Gateway
scp *.ipk root@<openwrt board ip>:/tmp/

Then SSh to your openwrt board and run

cd /tmp/
opkg update
opkg install libftdi
opkg install libmpsse_1.3-1_ramips_24kec.ipk
opkg install lora-gateway_1.3.0-1_ramips_24kec.ipk

Now you should have your lora utils in /root/lora if all goes well

Connect your lora board like the IMST ic880a or the RAK Wireless RAK831 (recommended for flexibility and ease of prototyping) via SPI and run the test utils

PM me if you need any specifics. There is a silicon bug in the MT7688 for which you may need to rebuild the firmware with the patch provided 
in another repo here:





