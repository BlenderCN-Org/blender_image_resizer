##Blender Image Resizer

######An image resizer addon for blender. Easily resize and save your images from blender.

[![Blender Image Resizer Youtube Video](http://img.youtube.com/vi/Rh3Y3nvFrGA/0.jpg)](http://www.youtube.com/watch?v=Rh3Y3nvFrGA)

####It needs the [Pillow(PIL)](https://pypi.python.org/pypi/Pillow) python module!

#####Known Issues:
For now, this add on can not save 16 bit images.
(pil does not support saving 16 bit images.)

###How to install Pillow to Blender?


**How to find blender's python version:**

Switch to python console in blender and type these commands.
    
```python
>>> import sys
>>> sys.version
'3.5.1 (default, Jun  7 2016, 02:56:20) \n[GCC 5.3.0]'
```
    
(means, version = 3.5.1)

</br>

**How to find the dist-packages(or site-packages) directory:**

Launch the matching version python interpreter from the terminal and type these commands. 
    
```python
import site; site.getsitepackages()
# or
import distutils.sysconfig; print(distutils.sysconfig.get_python_lib())
```
</br>

**How to find where to copy:**

Switch to python console in blender and type these commands.
```python
import sys
sys.path
```

These lines will list some paths that you can copy the PIL directory to them.
any of them will do.

</br>
</br>

####For Linux:
#####Alternative 1:

If matching version python with blender's python is not installed on your system, 
please try installing it first.

Now, try installing the Pillow with your package manager for your system's matching version python. 

than copy (or make a symlink) the PIL directory from the python's dist-packages(or site-packages) to your
`~/.config/blender/2.xx/scripts/modules/` directory 
_(or one of the directories from "How to find where to copy" title.)_

And it is done.  

</br>

#####Alternative 2:

_I will use python3.5 as an example for further instructions.
If you have an older version you should change the version numbers with matching yours._

**If your distro does not have the pillow package for matching version python:**

Install pillow dependencies, (we will also need python3.5-dev package)
_For Ubuntu / Mint_
    
    sudo apt-get python3.5-dev
    sudo apt-get install libtiff4-dev libjpeg8-dev zlib1g-dev libfreetype6-dev liblcms2-dev libwebp-dev tcl8.6-dev tk8.6-dev

install virtualenv

    sudo apt-get install python-virtualenv

create a python3 virtual environment

```python
cd ~
virtualenv -p /usr/bin/python3.5 myPilEnv

# switch to newly created environment
source myPilEnv/bin/activate

# now you should see on the command line (myPilEnv)aaa@asasd ~ $:
# that means we are in our virtual environment. 
# when we use pip in here, it will install the module to our virtual environment

# install pillow (no need to sudo)
pip install -U pillow

# hopefully it will be installed succesfully.

#and finally deactivate myPilEnv virtual environment
deactivate
```
    
now copy or (symlink) the PIL directory from 

`~/myPilEnv/lib64/python3.5/site-packages/PIL`
to

`~/.config/blender/2.77/scripts/modules`
_(or one of the directories from "How to find where to copy" title.)_

and hopefully it will work.


#####Alternative 3:

First we will install the "pip" directly to the blender's python.
After that we can easily install any 3rd party python module to blender's python.

If you have installed blender by downloading and extracting a zip file, 

please download [get-pip.py](https://pip.pypa.io/en/stable/installing/)

open a terminal and change directory to 
    
    cd /your-blender-path/2.77/python/bin/
    ls

Now you should see the python executable, it may be python3.5 or python3.5m

and install get-pip.py
_("./"  <-- these are important please do not omit them )_

    ./python3.5m /path/to/get-pip.py
if it is a success than install pillow directly to blender. 
    
    ./pip install -U pillow

And it is done.

If you encounter some compilation errors you may need to install the pillow dependencies.
To install pillow dependencies, (we may also need python3.5-dev package)
_For Ubuntu / Mint_
    
    sudo apt-get python3.5-dev
    sudo apt-get install libtiff4-dev libjpeg8-dev zlib1g-dev libfreetype6-dev liblcms2-dev libwebp-dev tcl8.6-dev tk8.6-dev
    
And try again installing pillow
    
    ./pip install -U pillow


####For Windows:

#####Alternative 1:

First, please install the exact same version python that we found earlier to windows.
If it is not already installed.

Python Installers: https://www.python.org/downloads/

(Scroll down to see other versions. And click the version name to see 32 or 64 bit versions of that version.)
Also if your blender is 32 bit. Your python version should be also 32 bit
if it is 64 bit than it should be 64 bit.

Download and install matching version Pillow installers from https://pypi.python.org/pypi/Pillow/3.3.0
Again versions should match.
For example for 64 bit Python 3.5
you should download "Pillow-3.3.0.win-amd64-py3.5.exe"
for 32 bit Python 3.5 "Pillow-3.3.0.win32-py3.5.exe".

You get the idea.

this will install the pillow to
`Yor_Python_Installation_Folder\Lib\site-packages`
as a folder named `PIL`

copy the `PIL` folder from
for example:

    C:\Program Files\Python35\Lib\site-packages\PIL
to

    C:\Users\<username>\AppData\Roaming\Blender Foundation\Blender\2.77\scripts\addons\modules

_(or one of the directories from "How to find where to copy" title.)_

And hopefully it is done.

#####Alternative 2:

If you have installed blender by downloading and extracting a zip file, 

Download pillow from http://www.lfd.uci.edu/~gohlke/pythonlibs/#pillow
Versions should match.
For example for 64 bit Blender and Python 3.5
you should download "Pillow-3.3.0-cp35-cp35m-win_amd64.whl"
for 32 bit Blender and Python 3.5
Pillow-3.3.0-cp35-cp35m-win32.whl
etc.

than go to your
`blender-folder\2.77\python\bin` and look for python.exe
if you see python exe
download get-pip.py from https://pip.pypa.io/en/stable/installing/ to any folder you want.
open a command line (from start menu search "cmd")
change dir to your-blender-folder-path\2.77\python\bin
for ex:

    cd C:\myBlender\2.77\python\bin
install pip, (you need the full path of get-pip.py)
for ex:

    python C:\Users\foo\Downloads\get-pip.py

if it is a success than install pillow

    ..\Scripts\pip.exe install c:\path\to\pil.whl

this will install pillow to 
`your-blender-folder-path\2.77\python\lib\site-packages\`
as a folder named `PIL`

copy PIL folder from
`your-blender-folder-path/2.77/python/lib/site-packages/PIL`
to
`C:\Users\<username>\AppData\Roaming\Blender Foundation\Blender\2.77\scripts\addons\modules`

_(or one of the directories from "How to find where to copy" title.)_

And hopefully it is done.

####For MAC OS X:

I don't have a mac, so

...

But i'll try...

The idea is, installing pillow to a python installation which is the same version as the blender's python.
And copying the newly installed PIL directory to a folder which blender looks for python modules or scripts.

_(Please see the titles at the begining of this document. "How to find the dist-packages(or site-packages) directory" and "How to find where to copy")_

First, please install the exact same version python that we found earlier to your system.
If it is not already installed.

Python OS X Installers: https://www.python.org/downloads/mac-osx/

_(Scroll down to see other versions.)_

Also if your blender is 32 bit. Your python version should be also 32 bit
if it is 64 bit than it should be 64 bit.

And normally using the matching version python's pip and executing this command should work.

    pip3 install -U pillow
    # or maybe pip3.5
    pip3.5 install -U pillow

if it does not work, please try this

    pip3 install wheel
    pip3 install --use-wheel pillow

if one of these works, than copy the PIL directory to a directory which blender scans for python modules (See above.)

But there may be some problems depending on your OS X version.
For example:
https://stackoverflow.com/questions/21867277/installing-pillow-with-mac-os-x-mavericks-10-9-1
etc.


**Also You can try [homebrew](http://brew.sh/)**

_(from http://stackoverflow.com/a/23594914)_

Homebrew provides a formula for Python 2.7.x and one for Python 3.x. They don't conflict, so they can both be installed. The executable python will always point to the 2.x and python3 to the 3.x version.

!! But you can not select the exact version of python3, you may need python 3.5 and it may install python 3.4.

So:

    $ brew update
    $ brew install python3

This also gives pip for Python 2 and pip3 for Python 3. So you can install Pillow like:

    $ brew install libtiff libjpeg webp little-cms2
    $ pip3 install pillow

and again if it works, and the python versions match,
than copy the PIL directory to a directory which blender scans for python modules (See above.)

Good luck.