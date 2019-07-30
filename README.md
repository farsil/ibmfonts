# IBM fonts
A collection of monospaced, bitmap fonts in BDF format that origin from IBM
text mode and system fonts. They include extended latin, greek, cyrillic and
hebrew scripts and several extra characters, for a total of 782 glyphs each.
The fonts are in BDF 2.1 format and fully compatible with applications that
make use of either Xft or XLFD.

# Installation
In order to install the fonts with default settings, run (if necessary as
root):

    $ git clone https://github.com/farsil/ibmfonts.git
    $ cd ibmfonts
    $ ./configure
    # make clean install

The default behaviour of `configure` is to look for sources in `./bdf`, compile
fonts in `./pcf`, and install the fonts in `/usr/local/share/fonts/misc`.
`configure` automatically creates `objdir` if it does not exist.

## AUR Package 
If you use Arch Linux, there is an AUR package for these fonts named
[ibm-fonts](https://aur.archlinux.org/packages/ibm-fonts/). You may use your
favourite AUR helper or proceed with manual installation as described
[here](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages).

# Configuration script
You can pass several command line arguments to `configure`:

    --prefix=<PATH>         Prefix for destination directories.
    --srcdir=<PATH>         Directory for the source font files.
    --objdir=<PATH>         Directory for the compiled font files.
    --installdir=<PATH>     Directory to install the fonts in.
    --bsd-make              Generate a bmake-friendly makefile.

If `srcdir` is set and is a relative path, its parent directory will be
`$(prefix)/src`. If `objdir` is set and is a relative path, its parent
directory will be `$(prefix)/obj`. If `installdir` is set and is a relative
path, its parent directory will be `$(prefix)/share/fonts`. If you don't want
this behaviour simply use absolute paths instead of relative ones.

# Removal
From the directory you cloned this repository into, run:

    # make uninstall

# Updating the font cache
After installation or removal, it is important to update the font cache to
reflect changes. For applications that use fontconfig, simply run:

	# fc-cache

Letting older applications like `xfontsel` detect the changes is more
complicated. First, check that the installation directory (I will assume it's
`/usr/local/share/fonts/misc` for the sake of the example) is in the X font
path. You can verify that by running:

	$ xset q

If it is not in the font path, you need to instruct X to read your font
directory by adding a `FontPath` entry under the `Files` section in
`/etc/X11/xorg.conf` (if the file does not exists, create it):

	Section "Files"
		# There might be other entries in the section
		FontPath "/usr/local/share/fonts/misc"
	EndSection

After making sure the installation directory is in the font path, run:

	# mkfontdir /usr/local/share/fonts/misc
	# mkfontscale /usr/local/share/fonts/misc
	$ xset fp rehash

You can check whether the font is detected by X by running either `xfontsel` or
`xlsfonts`.

# Font Preview 
## IBM BIOS 8x8
![IBM BIOS 8x8](https://farsil.github.io/ibmfonts/images/preview/dark/ib8x8u.png) [![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Ffarsil%2Fibmfonts.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2Ffarsil%2Fibmfonts?ref=badge_shield)
 
*XLFD name:* -ibm-bios-normal-r-normal--8-60-96-96-c-80-iso10646-1  
*Filename:* ib8x8u.bdf  

## IBM BIOS 16x8
![IBM BIOS 16x8](https://farsil.github.io/ibmfonts/images/preview/dark/ib16x8u.png)  
*XLFD Name:* -ibm-bios-normal-r-expanded--8-60-96-96-c-160-iso10646-1  
*Filename:* ib16x8u.bdf  

## IBM BIOS 16x16
![IBM BIOS 16x16](https://farsil.github.io/ibmfonts/images/preview/dark/ib16x16u.png)  
*XLFD Name:* -ibm-bios-normal-r-normal--16-120-96-96-c-160-iso10646-1  
*Filename:* ib16x16u.bdf  

## IBM BIOS 8x16
![IBM BIOS 8x16](https://farsil.github.io/ibmfonts/images/preview/dark/ib8x16u.png)  
*XLFD Name:* -ibm-bios-normal-r-condensed--16-120-96-96-c-80-iso10646-1  
*Filename:* ib8x16u.bdf  

## IBM CGA 8x8
![IBM CGA 8x8](https://farsil.github.io/ibmfonts/images/preview/dark/ic8x8u.png)  
*XLFD Name:* -ibm-cga-normal-r-normal--8-60-96-96-c-80-iso10646-1  
*Filename:* ic8x8u.bdf  

## IBM CGA 16x16
![IBM CGA 16x16](https://farsil.github.io/ibmfonts/images/preview/dark/ic16x16u.png)  
*XLFD Name:* -ibm-cga-normal-r-normal--16-120-96-96-c-160-iso10646-1  
*Filename:* ic16x16u.bdf  

## IBM CGA 8x16
![IBM CGA 8x16](https://farsil.github.io/ibmfonts/images/preview/dark/ic8x16u.png)  
*XLFD Name:* -ibm-cga-normal-r-condensed--16-120-96-96-c-80-iso10646-1  
*Filename:* ic8x16u.bdf  

## IBM CGA Light 8x8
![IBM CGA Light 8x8](https://farsil.github.io/ibmfonts/images/preview/dark/icl8x8u.png)  
*XLFD Name:* -ibm-cga-light-r-normal--8-60-96-96-c-80-iso10646-1  
*Filename:* icl8x8u.bdf  

## IBM CGA Light 16x16
![IBM CGA Light 16x16](https://farsil.github.io/ibmfonts/images/preview/dark/icl16x16u.png)  
*XLFD Name:* -ibm-cga-light-r-normal--16-120-96-96-c-160-iso10646-1  
*Filename:* icl16x16u.bdf  

## IBM CGA Light 8x16
![IBM CGA Light 8x16](https://farsil.github.io/ibmfonts/images/preview/dark/icl8x16u.png)  
*XLFD Name:* -ibm-cga-light-r-condensed--16-120-96-96-c-80-iso10646-1  
*Filename:* icl8x16u.bdf  

## IBM EGA 8x14
![IBM EGA 8x14](https://farsil.github.io/ibmfonts/images/preview/dark/ie8x14u.png)  
*XLFD Name:* -ibm-ega-normal-r-normal--14-100-96-96-c-80-iso10646-1  
*Filename:* ie8x14u.bdf  

## IBM EGA 16x14
![IBM EGA 16x14](https://farsil.github.io/ibmfonts/images/preview/dark/ie16x14u.png)  
*XLFD Name:* -ibm-ega-normal-r-expanded--14-100-96-96-c-160-iso10646-1  
*Filename:* ie16x14u.bdf  

## IBM EGA 9x14
![IBM EGA 9x14](https://farsil.github.io/ibmfonts/images/preview/dark/ie9x14u.png)  
*XLFD Name:* -ibm-ega-normal-r-normal--14-100-96-96-c-90-iso10646-1  
*Filename:* ie9x14u.bdf  

## IBM EGA 18x14
![IBM EGA 18x14](https://farsil.github.io/ibmfonts/images/preview/dark/ie18x14u.png)  
*XLFD Name:* -ibm-ega-normal-r-expanded--14-100-96-96-c-180-iso10646-1  
*Filename:* ie18x14u.bdf  

## IBM MDA 9x14
![IBM MDA 9x14](https://farsil.github.io/ibmfonts/images/preview/dark/im9x14u.png)  
*XLFD Name:* -ibm-mda-normal-r-normal--14-100-96-96-c-90-iso10646-1  
*Filename:* im9x14u.bdf  

## IBM VGA 8x16
![IBM VGA 8x16](https://farsil.github.io/ibmfonts/images/preview/dark/iv8x16u.png)  
*XLFD Name:* -ibm-vga-normal-r-normal--16-120-96-96-c-80-iso10646-1  
*Filename:* iv8x16u.bdf  

## IBM VGA 16x16
![IBM VGA 16x16](https://farsil.github.io/ibmfonts/images/preview/dark/iv16x16u.png)  
*XLFD Name:* -ibm-vga-normal-r-expanded--16-120-96-96-c-160-iso10646-1  
*Filename:* iv16x16u.bdf  

## IBM VGA 9x16
![IBM VGA 9x16](https://farsil.github.io/ibmfonts/images/preview/dark/iv9x16u.png)  
*XLFD Name:* -ibm-vga-normal-r-normal--16-120-96-96-c-90-iso10646-1  
*Filename:* iv9x16u.bdf  

## IBM VGA 18x16
![IBM VGA 18x16](https://farsil.github.io/ibmfonts/images/preview/dark/iv18x16u.png)  
*XLFD Name:* -ibm-vga-normal-r-expanded--16-120-96-96-c-180-iso10646-1  
*Filename:* iv18x16u.bdf  

# Credits
VileR from [The Ultimate Oldschool PC Font Pack](http://int10h.org/oldschool-pc-fonts/)
for his pixel-perfect reproductions of these old system fonts. I used his
PxPlus fonts as a base.


## License
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Ffarsil%2Fibmfonts.svg?type=large)](https://app.fossa.io/projects/git%2Bgithub.com%2Ffarsil%2Fibmfonts?ref=badge_large)