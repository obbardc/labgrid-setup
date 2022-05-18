Some things I'd like to improve on in the setup.


Features:
- DUT VLAN with optional network bridge
- Setup Wireguard configuration
- TFTP/NFS booting with on-device bootloader (SPI Flash / ability to flash a bootloader in known state?)
- Boot Rockchip loader (TODO: RKUSBLoader filter_match function is wrong)
- Flash Rockchip EMMC & GPIOs to disable EMMC
- Boot Sunxi


Simplifications / improvements:
- Use ESPHome API instead of MQTT; remove the MQTT broker
- Use Kubernetes or similar instead of systemd service files
- Automatically test / lint ansible playbook in branches
- Automatically run ansible playbook on git push to main
- Automatically update ESPHome firmware
