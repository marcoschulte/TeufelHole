# Basic Setup

Copy pi image to sd card

    diskutil list
    diskutil unmountDisk /dev/diskX
    sudo dd bs=1m if=/Users/mschulte/Downloads/2020-05-27-raspios-buster-lite-armhf.img of=/dev/rdiskX
    sync

Enable SSH

    touch /Volumes/boot/ssh
    diskutil umountDisk /dev/diskX

Start PI, connect ethernet. Copy your ssh key to pi, default login to pi is `pi`:`raspberry`.

Adapt `teufelhole-playbook.yml` to match your ips, change wifi ssid and password.

Enter raspberry pi IP into `ansible/inventories/hosts`.

Run ansible playbook

    ansible-playbook -i inventories/hosts teufelhole-playbook.yml 