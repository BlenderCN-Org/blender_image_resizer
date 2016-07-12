##Blender Image Resizer

######An image resizer addon for blender. Easily resize and save your images from blender.

[![Blender Image Resizer Youtube Video](http://img.youtube.com/vi/Rh3Y3nvFrGA/0.jpg)](http://www.youtube.com/watch?v=Rh3Y3nvFrGA)

#####It needs the [Pillow(PIL)](https://pypi.python.org/pypi/Pillow) python module!


####How to install Pillow to Blender?
If your system's python version matches with blender's python version,

(To find blender's python version, switch to python console in blender and type these commands.)

    >>> import sys
    >>> sys.version
    '3.5.1 (default, Jun  7 2016, 02:56:20) \n[GCC 5.3.0]'
    
(means, version = 3.5.1)

If pillow is not installed, first install it with;

For Windows:

    pip install -U pillow

For Linux and OS X:

    sudo pip install -U pillow

to your system's python.

And then, you can just copy the "PIL" directory form your system's python's site-packages directory
to blender's python's site-packages directory. :) 

#####Alternative pillow installation ways:
InshaAllah, soon ...


#####Known Issues:
For now, this add on can not save 16 bit images. 
(pil does not support saving 16 bit images.)


