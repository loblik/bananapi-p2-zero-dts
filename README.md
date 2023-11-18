# bananapi-p2-zero-dts

This repository contains BSP patches for Banana PI P2 Zero. Goal is to have board supported in upstream (both kernel and u-boot) and later also in Armbian.

## Armbian

To build the image.

```
./compile.sh BOARD=bananapip2zero BRANCH=curren KERNEL_CONFIGURE=no RELEASE=bookworm BRANCH=current BUILD_ONLY=default BUILD_MINIMAL=yes
```
