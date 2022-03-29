# Linux Notes

AMD Drivers: [https://www.amd.com/es/support/kb/release-notes/rn-amdgpu-unified-linux-20-20](https://www.amd.com/es/support/kb/release-notes/rn-amdgpu-unified-linux-20-20)

Wifi Driver missing on HP Envy x360 Ryzen 7:

To install wifi driver clone this repo: [https://github.com/lwfinger/rtw89](https://github.com/lwfinger/rtw89) the run the following commands:
```
cd rtw89
make
sudo make install
sudo modprobe -v rtw_8852ae
```
**Note:** If you get an error like operation not permitted the make sure the Secure Boot is disabled in the BIOS.

---
To add refresh button to the Right-click context menu run the following commands:

```
sudo add-apt-repository ppa:nae-team/ppa
sudo apt-get update
sudo apt-get install xdotool nautilus nautilus-refresh
nautilus -q
```

Create a file `nemo-refresh.desktop` with the following lines in `/usr/share/applications/` directory and then run `nautilus -q`: 

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
