This repo details how to install Archivematica using `vagrant`.

The aim is to be able to just clone this repo and run the instructions to have a working Archivematica instance, while also addressing some of the common troubleshooting steps and issues that may arise.

## Prerequisites
- [Vagrant](https://www.vagrantup.com/)
- [VirtualBox](https://www.virtualbox.org/)

## Installation
1. Clone this repo
  ```
  git clone https://github.com/Mycsina/archivematica-vagrant.git
  ```
2. Change into the directory
  ```
  cd archivematica-vagrant
  ```
3. Run Vagrant
  ```
  vagrant up
  ```
4. Access the Archivematica dashboard at [10.10.10.20](http://10.10.10.20)

## Troubleshooting

### Vagrant up fails
If you get an error complaining about VirtualBox:
  ```
  The provider 'virtualbox' that was requested to back the machine
  'default' is reporting that it isn't usable on this system. The
  reason is shown below:
  ```

You may need to load the VirtualBox kernel modules.
  ```
  sudo modprobe vboxdrv vboxnetadp vboxnetflt
  ```

If the modules are not installed, you can install them with:

  - Debian/Ubuntu: `sudo apt-get install virtualbox-dkms`
  - Arch: `sudo pacman -S virtualbox-host-dkms`