## SCREEN FLICKERING AMD GPU

The idea is to disable PSR in the grub boot, as the PSR is causing instability with AMDGPU & internal display:

```
sudo vi /etc/default/grub;

<...>
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash amdgpu.dcdebugmask=0x10"
<...>

sudo update-grub;
sudo reboot
```

## BLUETOOTH

Use the `bluetoothctl` terminal to connect to paired devices:

```
bluetoothctl;
```
