# Nextcloud-tutorial

Fast recap on my hardware choices and how I setup my cloud.

## Hardware
* Raspberry pi 4 4gb (for USB3.0)
* cooling HAT: https://fr.aliexpress.com/item/4000570741979.html
* 3 HHD 3.5" 1To: https://www.amazon.fr/gp/product/B0088PUEPK/
* FANTEC QB-35US3-6G: https://www.amazon.fr/gp/product/B00ORENYJE/
* 1 back-up SD card : https://www.amazon.fr/gp/product/B073K14CVB/

Total ~ 300€ (HDD included)

## Configuration

follow this tutorial: https://raspberrytips.com/install-nextcloud-raspberry-pi/

Activate:

nc-prettyURL
fail2ban
nc-automount

follow this tutorial: https://tailscale.com/download/linux/rpi

note: reboot before sudo tailscale up

nc-trusted-domains: the nextcloudpi machine's IP (starting with 100.) and the Search Domains with magic DNS (something like nextcloudpi.your.email.address.beta.tailscale.net) 

change your generated password with nc-passwd for nextcloudpi panel and in setting/security on nextcloud

activate two auth 

nc-format your 3 HDDs (one by one)

follow wizard

add backup & snapshot

configure cooling fan in python.
http://www.yahboom.net/study/RGB_Cooling_HAT

curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python3 get-pip.py
sudo apt-get install python3-smbus
python3 -m pip install --upgrade Pillow
sudo apt-get install python3-dev python3-rpi.gpio

add in your .bashrc: nohup python -u RGB_Cooling.py run --username RGB > /logs/main.log 2>&1 & echo $! > RGB.pid

add apps and enjoy!

some tips: https://www.linuxbabe.com/ubuntu/install-nextcloud-ubuntu-20-04-apache-lamp-stack

## Android Support

I am using Nextcloud, Tailscale, Notes, and Ncphotos apps.
To enable video previews one the latter: https://gitlab.com/nkming2/nc-photos/-/wikis/help/video-previews


