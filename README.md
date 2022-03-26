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
