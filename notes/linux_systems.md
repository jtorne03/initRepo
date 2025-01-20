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

## GIT 

For the formatting of branches, we need to `source /path/to/git-prompt.sh` and add the following the `PS1='<...>'` field, within the quotes:

```
'\[\033[38;2;255;165;0m\]$(__git_ps1 " (%s)") \[\033[00m\]\n\$'
```

This will format the git branch in the PS1, with the color orange.
