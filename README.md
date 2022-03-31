# Linux Notes

## Missing Wifi drivers in AMD

First, try to install the AMD Drivers from here: [https://www.amd.com/es/support/kb/release-notes/rn-amdgpu-unified-linux-20-20](https://www.amd.com/es/support/kb/release-notes/rn-amdgpu-unified-linux-20-20). If it gives some error then try the following option.

I had the Wifi Driver missing issue on HP Envy x360 Ryzen 7. To install wifi driver clone this repo: [https://github.com/lwfinger/rtw89](https://github.com/lwfinger/rtw89) then run the following commands:
```
cd rtw89
make
sudo make install
sudo modprobe -v rtw_8852ae
```
**Note:** If you get an error like operation not permitted the make sure the **Secure Boot** is **disabled** in the BIOS.


## Adding Refresh button to the right-click Context Menu in Linux Mint/Ubuntu/Debian

To add refresh button to the Right-click context menu run the following commands:

```
sudo add-apt-repository ppa:nae-team/ppa
sudo apt-get update
sudo apt-get install xdotool nautilus nautilus-refresh
nautilus -q
```

Create a file `nemo-refresh.desktop` (https://github.com/kelebek333/nemo-actions/blob/master/usr/share/nemo/actions/nemo-refresh.nemo_action) with the following lines in `/usr/share/applications/` directory and then run `nautilus -q`: 

```
[Nemo Action]
Name=Refresh
Name[tr]=Tazele
Comment=Nemo Refresh
Exec=xdotool key ctrl+r
Selection=None
Extensions=any;
Icon-Name=view-refresh
Dependencies=xdotool;
```

## Disable Caps lock

To disable caps-lock in Linux Mint or any other Linux distro run the following command:

```
setxkbmap -option caps:none
```

or, Navigate to Layouts > Options in the Keyboard and then expand the Caps Lock behavior and then select **Caps Lock is disabled**.

