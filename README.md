## Recovery Device Tree for the Samsung Galaxy A12 (MTK)

## How-to compile it:

# Create dirs
$ mkdir tw; cd tw

# Init repo
$ repo init --depth=1 -u https://github.com/minimal-manifest-twrp/platform_manifest_twrp_aosp.git -b twrp-11

# Clone a12 tree
$ git clone https://github.com/Nikolay1257/android_device_samsung_a12 device/samsung/a12

# Sync
$ repo sync

# Build
$ export ALLOW_MISSING_DEPENDENCIES=true; . build/envsetup.sh; lunch twrp_a12-eng; mka recoveryimage

# Disable File Based Encryption (FBE) after installing TWRP.
$ Boot TWRP; format DATA partition; start TWRP SHELL; execute: multidisabler.
Your DATA partition will be secured against re-encryption.


Blobs version:
> Kernel base: Compiled from source A125FXXU2BVG6 [Kernel] (https://github.com/Nikolay1257/android_kernel_samsung_a12)

