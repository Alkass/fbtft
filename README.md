# FBTFT
Linux Framebuffer drivers for small TFT LCD display modules.
The module 'fbtft' makes writing drivers for some of these displays very easy.

Development is done on a Raspberry Pi running the Raspbian "wheezy" distribution.

# INSTALLATION
  Download kernel sources

  From Linux 3.15  
    cd drivers/video/fbdev
    git clone https://github.com/notro/fbtft.git
    
    Add to drivers/video/fbdev/Kconfig:   source "drivers/video/fbdev/fbtft/Kconfig"
    Add to drivers/video/fbdev/Makefile:  obj-y += fbtft/
