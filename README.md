# Nextcloud-tutorial

Fast tutorial on my hardware choice and how I setup my cloud

## Hardware
* Raspberry pi 4 4gb (for USB3.0)
* cooling HAT: https://fr.aliexpress.com/item/4000570741979.html
* 3 HHD 3.5" 1To: https://www.amazon.fr/gp/product/B0088PUEPK/
* FANTEC QB-35US3-6G: https://www.amazon.fr/gp/product/B00ORENYJE/
* 1 back-up SD card : https://www.amazon.fr/gp/product/B073K14CVB/

Total ~ 300€ (HDD included)

## Configuration

follow this tutorial:
https://raspberrytips.com/install-nextcloud-raspberry-pi/

enable SSH
ifconfig

then in SSH: 
sudo apt update
sudo apt upgrade
sudo ncp-config
Activate:

nc-prettyURL
nc-webui
fail2ban
nc-automount

https://tailscale.com/download/linux/rpi
note: reboot before sudo tailscale up

nc-trusted-domains: the nextcloudpi machine's IP (starting with 100.) and the Search Domains with magic DNS (something like nextcloudpi.your.email.address.beta.tailscale.net) 

change your generated password with nc-passwd for nextcloudpi panel and in setting/security on nextcloud
activate two auth 

nc-format your 3 HDDs (one by one)
follow wizard
add backup & snapshot
add apps and enjoy!