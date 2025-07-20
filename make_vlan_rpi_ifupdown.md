# step one: install tooles

```bash
sudo apt install ifupdown bridge-utils
```

# step two: write config file

sample belo:

```
# This file describes the network interfaces available on your system
# and how to activate them. For more information, see interfaces(5).
source /etc/network/interfaces.d/*

# The loopback network interface
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet manual

auto wlan0
iface wlan0 inet manual
#    wpa-conf /etc/wpa_supplicant/wpa_supplicant.conf


auto eth0.40
iface eth0.40 inet static
    address 10.1.40.4
    gateway 10.1.40.1
    dns-nameservers 1.1.1.1    1.0.0.1
    vlan-raw-device eth0
```

# step 3: disable and enable services.

```bash
sudo systemctl disable NetworkManager
sudo systemctl enable networking
```


# step 4: reboot pie

```bash
sudo reboot now
```
