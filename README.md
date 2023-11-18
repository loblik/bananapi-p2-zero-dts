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
