# Evic : Mise à jour du micrologiciel de la cigarette électronique Eleaf iStick Pico

## I Installation

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

4) Lancer la compilation
```
    $ python setup.py install
```
![03-python setup.py install](https://raw.githubusercontent.com/KevinMinions/python-evic/master/.images/03-python%20setup.py%20install.png)

5) Puisque le script ``setup.py`` n'a pas réussi à télécharger l'archive correctement (pour une raison inconnue), j'ai dû télécharger "manuellement" [setuptools-40.5.0.zip](https://pypi.python.org/packages/source/s/setuptools/setuptools-40.5.0.zip), en la plaçant à la racine du dossier ``python-evic``.

6) Deuxième tentative de compilation
```
    $ python setup.py install
```
![04-python setup.py install](https://raw.githubusercontent.com/KevinMinions/python-evic/master/.images/03bis-python%20setup.py%20install.png)

7) Puisque le compte utilisateur n'est pas suffisant, je passe en ``superutilisateur``
```
    $  sudo -s
```
![05-sudo -s](https://raw.githubusercontent.com/KevinMinions/python-evic/master/.images/05-sudo%20-s.png)

8) Troisième tentative de compilation
```
    $ python setup.py install
```
![06-python setup.py install 01](https://raw.githubusercontent.com/KevinMinions/python-evic/master/.images/06-python%20setup.py%20install%2001.png)

![07-python setup.py install 02](https://raw.githubusercontent.com/KevinMinions/python-evic/master/.images/07-python%20setup.py%20install%2002.png)

![08-python setup.py install 03](https://raw.githubusercontent.com/KevinMinions/python-evic/master/.images/08-python%20setup.py%20install%2003.png)

9) Ajouter les identifiants USB
Copier ``99-nuvoton-hid.rules`` (présent dans le dossier ``python-evic/udev/``) et le coller dans ``/etc/udev/rules.d/``

:hugs: :hugs: :hugs: :hugs: :hugs: :hugs: :hugs: :hugs: :hugs: :hugs:

**Installation terminée !**

:hugs: :hugs: :hugs: :hugs: :hugs: :hugs: :hugs: :hugs: :hugs: :hugs:


## II Mise à jour du micrologiciel de la cigarette électronique Eleaf iStick Pico
*Pas besoin d'être ``superutilisateur`` pour éxécuter ces manipulations*

1) Connecter la ``cigarette électronique Eleaf iStick Pico`` à l'ordinateur

2) Sauvegarde du micrologiciel actuellement installé sur la cigarette électronique
```
    $ evic-usb dump-dataflash -o "[chemin du répertoire]/out.bin"
```
![09-evic-usb dump-dataflash -o](https://raw.githubusercontent.com/KevinMinions/python-evic/master/.images/09-evic-usb%20dump-dataflash.png)

3) Téléchargement et extraction du [micrologiciel](http://www.eleafworld.com/softwares-for-istick-pico/) sur le site officiel (version pour Windows)
![11-iStick_Pico_V1.03.zip](https://raw.githubusercontent.com/KevinMinions/python-evic/master/.images/11-iStick_Pico_V1.03.zip.png)

4) Mise à jour du micrologiciel de la cigarette électronique Eleaf iStick Pico
```
    $ evic-usb upload "[chemin du répertoire]/iStick_Pico_Vx.xx.bin"
```
![10-evic-usb upload](https://raw.githubusercontent.com/KevinMinions/python-evic/master/.images/10-evic-usb%20upload.png)

:hugs: :hugs: :hugs: :hugs: :hugs: :hugs: :hugs: :hugs: :hugs: :hugs:

**Mise à jour du micrologiciel terminée !**

:hugs: :hugs: :hugs: :hugs: :hugs: :hugs: :hugs: :hugs: :hugs: :hugs:

### III Bonus : Personnaliser le logo affiché sur l'écran de la cigarette électronique Eleaf iStick Pico

1) Créer un fichier ``LOGO.bmp`` avec [Gimp](https://www.gimp.org/) par exemple

*L'archive de mise à jour du micrologiciel contient un fichier ``LOGO.bmp``*
![11-iStick_Pico_V1.03.zip](https://raw.githubusercontent.com/KevinMinions/python-evic/master/.images/11-iStick_Pico_V1.03.zip.png)

2) Envoie du fichier fichier ``LOGO.bmp`` dans la cigarette électronique Eleaf iStick Pico
```
    $ evic-usb upload-logo "[chemin du répertoire]/LOGO.bmp"
```
![12-evic-usb upload-logo](https://raw.githubusercontent.com/KevinMinions/python-evic/master/.images/12-evic-usb%20upload-logo.png)

![13-Exemple evic-usb upload-logo](https://raw.githubusercontent.com/KevinMinions/python-evic/master/.images/13-Exemple%20evic-usb%20upload-logo.png)

:hugs: :hugs: :hugs: :hugs: :hugs: :hugs: :hugs: :hugs: :hugs: :hugs:
