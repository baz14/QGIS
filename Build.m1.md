# Create `QGIS DMG file` using MacPorts (Apple Silicon)

## [Install prerequisites](https://www.macports.org/install.php)

- Install Apple's Command Line Developer Tools:
  ```bash
  xcode-select --install
  ```

- Install MacPorts for your version of the Mac operating system  
https://www.macports.org/install.php

## [Build QGIS via MacPorts](https://qgis.org/resources/installation-guide/#macports)
- Get information of a port:
  ```bash
  sudo port info qgis3
  ```
- Install port, e.g with GRASS GIS:
  ```bash
  sudo port install qgis3 +grass
  ```
- Update:
  ```bash
  sudo port selfupdate
  sudo port upgrade outdated
  ```
  
## Create a DMG installer
- Build a metapackage
  ```bash
  sudo port mpkg qgis3 +grass
  ```
- Wrap it into a DMG file:
  ```bash
  sudo port mdmg qgis3 +grass
  ```
- Find the generated DMG
  ```bash
  find /opt/local/var/macports -name '*.dmg' | tail -n 1
  ```
