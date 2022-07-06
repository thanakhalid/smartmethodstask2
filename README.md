# smartmethodstask2

task2:download ROS2 in jetson nano:
1-install ubuntu,preferablly custom one for jetson nano
2-then we need a way to flash the image into our sd card,for example balena etcher 
3-now we need to extract the zip file we downloaded , the command to extract the Ubuntu image: tar -xvjf Xubuntu-20.04-l4t-r32.3.1.tar.tbz2
4-now to flash the image, select the image in etcher, select target for example micro SD then click flash
5-go to the SD card that you flashed then go to boot then extlinux.conf, add the following in the file in label: FDT /boot/tegra210-p3448-0000-p3449-0000-b00.dtb
notes: 
To find out which .dtb file is compatible with your Nano run the following on the Nano (e.g. with official Nvidia image): cat /sys/firmware/devicetree/base/compatible
This command could also work instead: fdtget /boot/dtb/*.dtb / compatible
If you have the Jetson Nano B01, you have to add the following line in the extlinux.conf: FDT /boot/tegra210-p3448-0000-p3449-0000-b00.dtb
6-eject the SD file,put the sd card in the jetson nano 
7- you will be bot into ubunto
8-the just install ROS into the ubuntu like the documation in this link:http://docs.ros.org/en/rolling/Installation/Alternatives/Ubuntu-Development-Setup.html
