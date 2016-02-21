# FBTFT
Linux Framebuffer drivers for small TFT LCD display modules.
The module 'fbtft' makes writing drivers for some of these displays very easy.

Development is done on a Raspberry Pi running the Raspbian "wheezy" distribution.

# Installation

```bash
    sudo apt-get install bc
    git clone --depth=1 https://github.com/raspberrypi/linux
    cd linux
    pushd .
    cd drivers/video/fbdev
    git clone https://github.com/alkass/fbtft.git
    echo 'source "drivers/video/fbdev/fbtft/Kconfig"' >> Kconfig
    echo 'obj-y += fbtft/' >> Makefile
    popd
    KERNEL=kernel7
    make bcm2709_defconfig
    make -j4 zImage modules dtbs
    sudo make modules_install
    sudo cp arch/arm/boot/dts/*.dtb /boot/
    sudo cp arch/arm/boot/dts/overlays/*.dtb* /boot/overlays/
    sudo cp arch/arm/boot/dts/overlays/README /boot/overlays/
    sudo scripts/mkknlimg arch/arm/boot/zImage /boot/$KERNEL.img
```
