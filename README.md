git clone https://github.com/Greg798100/Orangepi-r1-openwrt.git

cd Orangepi-r1-openwrt
git branch -a
git checkout origin/openwrt-22.03.5
./scripts/feeds update -a
./scripts/feeds install -a
make menuconfig
make -j5 V=-1sc
