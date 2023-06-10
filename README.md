<h3 align="left">openwrt 22.03.5 for orangepi r1 worked wifi modules rtl8189es ap and client</h3>
### openwrt 22.03.5 for orangepi r1 worked wifi modules rtl8189es ap and client
<h4 align="left">how build</h4>

```sh
$ git clone https://github.com/Greg798100/Orangepi-r1-openwrt.git
$ cd Orangepi-r1-openwrt
$ git branch -a
$ git checkout origin/openwrt-22.03.5
$ ./scripts/feeds update -a
$ ./scripts/feeds install -a
$ make menuconfig
$ make -j5 V=-1sc
```
### Many thanks community
- [Openwrt](https://github.com/openwrt/openwrt)
- [Immortalwrt](https://github.com/immortalwrt/immortalwrt) https://github.com/jwrdegoede/rtl8189ES_linux
- [Jwrdegoede](https://github.com/jwrdegoede/rtl8189ES_linux)
<h4 align="left">and other</h4>
