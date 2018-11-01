
Evic : Mise à jour du micro logiciel de la cigarette électronique Eleaf iStick Pico
===============================

1) Installation des bibliothèques nécessaires ``python-hidapi`` et ``libusb-1.0-0-dev``

2) Récupération du code source “Evic”
```
    $ cd "[chemin du répertoire]" && git clone https://github.com/Ban3/python-evic.git
```
![01-git clone](https://raw.githubusercontent.com/KevinMinions/python-evic/master/.images/01-git%20clone.png)
  
    

3) Se placer dans le repertoire du code source
```
    $ cd python-evic
```
![02-cd python-evic](https://raw.githubusercontent.com/KevinMinions/python-evic/master/.images/02-cd%20python-evic.png)

    $ python setup.py install


Allowing non-root access to the device
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The file ``udev/99-nuvoton-hid.rules`` contains an example set of rules for setting the device permissions to ``0666``.  Copy the file to the directory ``/etc/udev/rules.d/`` to use it.

Usage
-------
See  ``--help`` for more information on a given command.

evic-convert
^^^^^^^^^^^^
``evic-convert`` is a tool to encrypt/decrypt firmware images:

::

    $ evic-convert in.bin -o out.bin

evic-usb
^^^^^^^^^^^^
``evic-usb`` is a tool for interfacing with the device through USB.


Dump device data flash to a file:

::

    $ evic-usb dump-dataflash -o out.bin

Upload an encrypted firmware image to the device:

::

    $ evic-usb upload firmware.bin

Upload an unencrypted firmware image to the device:

::

    $ evic-usb upload -u firmware.bin

Upload a firmware image using data flash from a file:

::

    $ evic-usb upload -d data.bin firmware.bin

Use  ``--no-verify`` to disable verification for APROM or data flash. To disable both:

::

    $ evic-usb upload --no-verify aprom --no-verify dataflash firmware.bin

    © 2018 GitHub, Inc.
    Terms
    Privacy
    Security
    Status
    Help

    Contact GitHub
    Pricing
    API
    Training
    Blog
    About

Press h to open a hovercard with more details.
