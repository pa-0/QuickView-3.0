# QuickView-2.8-modified
Modification of [QuickView-2.8 by Jundai](https://www.deviantart.com/jundai/art/QuickView-129693435) to support transparent PNG files and more.

Tiny picture viewer application that always stays on top and actually makes transparent regions of images (as well as any pixel with #010000 color) transparent and clickthrough. Similar to [cthrough](http://cthruview.sourceforge.net/) but the actual visible image parts aren't clickthrough and you dont need an extra window open to configure the options (nor does it choke your ram).

I have no idea how and why half of this works. I do not know if this works outside of Windows

The way the transparency works is it searches for #010000 pixels and makes those transparent (transparent PNG regions included), so basically you can just color what you want to be transparent in #010000 (just "black", aka #000000 doesn't work because titlebar is also considered to be "black").

**Known issues:**
```
- GIF doesn't work properly yet.
```

Example for Transparent PNG (the duck) with no borders (Transparency=1, HideCaption=1):

![Screenshot](/screenshot.png)


**Usage**
```
  1. Picture file (.bmp, .jpg, .gif, .png) drag and drop to this program.
  2. Select the [Open...] menu item from right click pulldown menu.
  3. Give picture file name from command line argument.
     e.g.  > QuickView.exe E:\pic\foo.png
```
**Right click pulldown menu**
```
  1. [New Window...]   (ctrl+N)
     Open picture file to new window.
  2. [Open...]         (ctrl+O)
     Open picture file to current window.
  3. [View as]
     To select zoom percentage.
  4. [Resize...]
     Zoom percentage.
  4. [Transparent...]
     Transparent mode. (0-255)
  5. Vertical Flip
  6. Horizontal Flip
  7. Pin
     Locks it in place so it cant be moved (can still be moved via title bar).
  8. [Exit]            (Esc)
     Quit the program.
```
**Initialize file (QuickView.ini)**
```
  Background - Set default background picture.(only BMP file)
  Icon - Set application icon.
  Title - Set window title.
  HideCaption - set '1' to hide window caption.
  NoTitle - Set '1' to hide window title text on titlebar.
  NoPictureName - Set '1' to only show Title on titlebar.
  NoTaskbarTitle - Set '1' to hide taskbar button.
  DisableMinimize - Set '1' to disable minimize button on titlebar.
  Transparency - Set '1' to enable transparent Window.
```

**fix_black.py**
```
python fix_black.py [filename]
```

Because transparency works the way it does, this program helps fix the black pixels in png images that shouldn't be transparent (changes all pixels with #010000 to #000000). Uses [numpy](https://pypi.org/project/numpy/) and [Pillow](https://pypi.org/project/Pillow/)

**Building and modifying**

If you wanna build and or edit it yourself i've been using the [Delphi IDE](https://www.embarcadero.com/products/delphi/starter). Just open the .dproj files with that.

**License**

  [Creative Commons Zero(CC0)](http://creativecommons.org/publicdomain/zero/1.0/)