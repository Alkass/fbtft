# FBTFT
Linux Framebuffer drivers for small TFT LCD display modules.
The module 'fbtft' makes writing drivers for some of these displays very easy.

Development is done on a Raspberry Pi running the Raspbian "wheezy" distribution.

# INSTALLATION
  Download kernel sources

  From Linux 3.15
    git clone https://github.com/alkass/linux
    cd linux/drivers/video/fbdev && git clone https://github.com/alkass/fbtft.git
    echo 'source "drivers/video/fbdev/fbtft/Kconfig"' >> Kconfig
    echo 'obj-y += fbtft/' >> drivers/video/fbdev/Makefile
