# Patch Marlin firmware and build for Ender 3 Max with BLTouch (or CRTouch) support

Goto Marlin Firmware server at https://marlinfw.org/meta/download/ and download the latest release/bugfix
and the corresponding Configuration zip files

Unzip the two folder in someplace

Copy over the Ender3Max Configuration (and overwrite as necessary) any files with the <root>/Marlin/ folder
Let us assume the two zip files are in the current dir ("."). Names shown below as of 1st Jan 2022 (latest release was 2.0.9.3 and released as 2.0.x branch)
## Download save the source code
```
unzip Marlin-bugfix-2.0.x.zip
unzip Configurations-bugfix-2.0.x.zip
cd Marlin-bugfix-2.0.x/Marlin
cp ../../Configurations-bugfix-2.0.x/config/examples/Creality/Ender-3\ Max/*.h .
```
## Patch the filee
From the Marlin subfolder where the Configuration.h and Configuration\_adv.h files are located, run:
```
git apply ender3max-crtouch.patch
```
Ignore any Warning you may get - any errors, you need to figure out deeper
## Build the firmware
Now: Go ahead and build it within VS Code, with PlatformIO and Marlin Build Manager plugins
If successful, you will find a firmware-*.bin file within the <root>/.pio/build/STM32F103RET6_creality/ folder
##### TODO: Download from the site with some scripting..
//body[1]/div[3]/div[1]/table[1]/tbody[1]/tr[2]/td[3]/a[1]
//body[1]/div[3]/div[1]/table[1]/tbody[1]/tr[2]/td[4]/a[1]

