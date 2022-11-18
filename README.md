# FlipperZero_plugin_howto
A simple plugin for the FlipperZero written as a tutorial example [ie. excessive documentation &amp; error handling]

If you wish to review this repository at the last point before the FAP update, use [this link](https://github.com/csBlueChip/FlipperZero_plugin_howto/tree/21f2620035728cd04e1951c3f6a30de1cfe8a280)

If you wish to review the (trivial) change[s] required to convert from the old "plugin" system to the new "FAP"/"Application" system, see [this link](https://github.com/csBlueChip/FlipperZero_plugin_howto/commit/91e06b53d5b9499edd7247b9b87b73e867f1a841#diff-277dc3e809211402bcdb4976c80cd9f172ede7d3c4f8b95137c00b51c236d71d) ...the addition of an icon and a sub-folder are optional.

# FAP Support Has Arrived! :)
Since the move to FAP, your "plugins" are now known as "applications"
* "Plugins" are 
  * Compiled in to the kernel
  * Flashed as part of the firmware in the main SoC
  * Require the developer to edit/maintain `/applications/meta/applications.fam`
* "Applications" are 
  * Compiled as separate programs
  * Live on the SDCard
  * Do NOT require code edits outside their own directory

The upshot is easier development, and (essentially) unlimited features on your Flipper!

# If you have not yet installed the FlipperZero devkit
```
mkdir -p ~/flipperZero/official/
cd ~/flipperZero/official/
git clone --recursive  https://github.com/flipperdevices/flipperzero-firmware.git  ./
./fbt
```
...and wait while it downloads all the required tools and performs the first build of the code.

# Install the cutting-edge firmware on your Flipper
`./fbt flash_usb_full`

Note:
* `flash_usb` is used to install JUST the firmware<br/>
* `flash_usb_full` also installs the "resources" (images and such)<br/>

Be aware that since the introduction of FAP, Applications are Resources (in the same way that Images are Resources).

# After the devkit is installed
Assuming your devkit is in: `~/flipperZero/official/`<br/>
...checkout this demo with:
```
cd ~/flipperZero/official//applications_user
mkdir bc_demo
cd bc_demo
git clone https://github.com/csBlueChip/FlipperZero_plugin_howto.git ./
```

# After bc_demo is downloaded
Compile with:
```
cd ~/flipperZero/official/
./fbt fap_bc_demo
```
...And/Or (Compile and) Upload with:
```
cd ~/flipperZero/official/
./fbt launch_app APPSRC=bc_demo
```
...Flashing will fail if the FlipperZero is in the applications menu, or running an application!

# About the bc_demo code & documentation
* Review the `README.txt` file for an overview of the code, and how to get started.
* Take a look in `bc_demo.c` for, frankly, an abusive amount of commenting; and overkill error-handling.

The code is all M.I.T. Licensed ...take it ...use it ...butcher it ...polish it ...whatever. <br/>
...If you do anything cool with it, I'd love to see your creation :)
