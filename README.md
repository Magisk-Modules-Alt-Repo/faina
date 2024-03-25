# "pm Install" from anywhere

Allow the `pm` CLI utility to install APKs from anywhere in your filesystem.

This is done by modifying the SELinux policy to allow system processes running under the user `system_server` to read APK files from `fuse` and `sdcardfs` filesystems.

## Background

At some point between the release of Android 8 and 9, Google changed the way the `pm install` utility handles APK installation. Before that change, you could install APKs from anywhere in your filesystem, but now you are required to provide an APK from a "trusted location" like `/data/local/tmp` to be able to install it.

This is annoying because it makes you run additional commands or take extra actions (e.g., copy, move, change file permissions) to move or copy the APK to a trusted location before actually installing it.

## Supported Android versions

This module was only tested on Android 14, but in theory, it should work on any Android version starting from Android Oreo.
