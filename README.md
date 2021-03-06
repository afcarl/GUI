# GUI

A python3 tkinter ttk based graphical user interface for CoolProp

Any help on development is welcome

The GUI requires CoolProp >5, matplotlib, numpy, scipy and Pillow to work
see requirements.txt taken from my Python 3.4 64 bit Windows install

for me it works on Ubuntu 14.04, Windows 7,8,8.1 and OS X (ugly on OS X)

To compile a .exe cx_freeze is required too, a build file 'create_EXE.py' is 
provided for Windows. add 'build' as parameter to run the create_EXE.py
With Ubuntu just run freeze on the cpgui.py

To create an installable package nsis and the HM nsis editor on windows work nicely

General features :
- usage of Coolprop and Refprop fluids and mixtures
- different input and output units
- english and german version 
- mixture setup by mass fractions
- calculate state points
- calculate simple saturation tables
- calculate a simple refrigeration cycle and cycle with internal hx
- rudymentary plots
- simple extensibility, anyone who knows Python 3, tkinter and thermodanamics can extend the GUI
- reduced complexity of GUI functions with input form generator using a data structure

Issues :
- still many
- No plots for mixtures
- Many issues with mixtures and plots
- no scaling of entropy and enthalpy yet (reference of state)

Next steps :
- add scaling for reference of state for entropy and enthalpy (IIR, ASHRAE, NBP ... )
- add help system


# Installation with conda

Please be aware that in some conda packages like pillow and matplotlib the tkinter support is broken.
These packages must be installed from another source to make tk/tkinter work.

If you use the conda package manager for Python, you might these commands 
useful. This is what I tried on a 32-bit Debian Linux machine:

- conda create -n py3k python=3 Cython numpy scipy six pip
- source activate py3k
- pip install pillow matplotlib
- pip install coolprop
- python cpgui.py 

... and you should be up and running

On Windows this will do (example) :

conda create -n cpgui33 python=3.3

activate cpgui33

conda install -n cpgui33 scipy

pip install --find-links http://www.lfd.uci.edu/~gohlke/pythonlibs/ -U --force-reinstall pillow matplotlib

pip install CoolProp

python cpgui.py




