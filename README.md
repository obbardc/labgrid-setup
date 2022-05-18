# Labgrid setup

This is my home Labgrid setup. Feel free to inspect, correct and find bugs as you like.


## Hardware configuration

TODO: Fill me in.


## Software configuration

The system controller is a Raspberry Pi. The basic setup is to install Raspbian
then set the hostname to `labgrid-exporter-0001`.

The software on the Raspberry Pi is automatically configured and updated with
Ansible. To setup Ansible, on your Debian workstation, run:

```
sudo apt install ansible
```

Then run the following command to setup the Pi:
```
ansible-playbook playbooks/all.yaml
```

It will take a few minutes, then everything is complete. If it goes wrong, just
format the SD card and re-start. Amazing!


## Useful tips

### Find device's udev match string

On the exporter, run the follwoing command and plug the device in:
```
$ sudo udevadm monitor --udev --property
ID_PATH=<path_string>
```

- For USB serial devices, use entries marked `DEVTYPE=usb_interface`
- For Rockchip loaders, use entries marked `DEVTYPE=usb_device`

### Listen to all MQTT publications
```
$ mosquitto_sub -v -h labgrid-exporter-0001 -p 1883 -t '#'
```
