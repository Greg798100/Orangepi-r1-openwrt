<h3 align="left">openwrt 22.03.5 for orangepi r1 worked wifi modules rtl8189es ap and client</h3>

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
- [OpenWrt Routing](https://github.com/openwrt/routing): Packages specifically focused on (mesh) routing.
### Support Community
  - Support Chat: group [@ctcgfw_openwrt_discuss](https://t.me/ctcgfw_openwrt_discuss) on [Telegram](https://telegram.org/).
  - Support Chat: group [#immortalwrt](https://matrix.to/#/#immortalwrt:matrix.org) on [Matrix](https://matrix.org/).
