# Vulnhub

## 1. Download a VulnHub machine

Go to VulnHub and choose a machine.
For a first machine, something like Kioptrix or Mr-Robot is a reasonable starting point.
Download the VM. Depending on the machine, you'll typically get an archive containing an .ova, .ovf + .vmdk, or VMware files.

## 2. Extract the download

On Kali, you can extract common archives with:
7z x downloaded-machine.zip
or:
tar -xf downloaded-machine.tar.gz
You should end up with the VM files.

3. Import it into VirtualBox

If you received an .ova:
Open VirtualBox.
Select File → Import Appliance.
Select the VulnHub .ova.
Click Next.
Review the VM settings.
Click Import.
VulnHub's own FAQ describes this as the standard VirtualBox import procedure. �
VulnHub
If you received an .ovf, select the .ovf file during the import process instead.

4. Put the VulnHub VM on an isolated network

...