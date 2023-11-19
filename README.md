# bananapi-p2-zero-dts

This repository contains BSP patches for Banana PI P2 Zero. Goal is to have board supported in upstream (both kernel and u-boot) and later also in Armbian.

## Armbian

Clone armbian build repository and change to it.

```
git clone git@github.com:armbian/build.git
cd build
```
Copy in the userpatches directory from this repository.

```
cp -r ../bananapi-p2-zero-dts/userpatches .
```

To build the image.

```
./compile.sh BOARD=bananapip2zero BRANCH=curren KERNEL_CONFIGURE=no RELEASE=bookworm BRANCH=current BUILD_ONLY=default BUILD_MINIMAL=yes
```

## Board revision 1.0

First revision of the board has different SD card holder with inverted polarity. This repository supports later versions, however with simple hack it is possible to make the board believe the card is inserted. Simply put a piece of paper between holder case and contact spring inside the holder, before inserting the card fully in. This is probably not a good long term solution, but if you just want to boot from SD card to install system on eMMC it's good enough.

![Board revision 1.0 SD-card hack](doc/rev_1_0_sd_card_hack.jpeg?raw=true "Board revision 1.0 SD-card hack")


## Development notes

Update SPL on eMMC.

```
dd obs=1 seek=8192 if=/tmp/sunxi-spl.bin of=/dev/mmcblk2
```
