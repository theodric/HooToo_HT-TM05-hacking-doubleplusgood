#HooToo HT-TM05 hacking stuff and junk
####theodric's edition

20160525:
* Updated Download-and-split script to grab the latest firmware file, and to use unrar rather than unzip since the archive type has changed. Also updated the relevant variable name to reflect. That's it.
* Added checksum script "checksum_tool.sh"
* Added mksquashfs script "squish.sh"
* Removed the HooToo firmware to avoid possibly drawing their ire. It's available elsewhere. No need for a mirror here.


------------------------------------------------------------------------------------------------------------------------------------
What follows below is a portion of the original readme from cryptographrix's repo, where the Download-and-split.sh script came from.
See: https://github.com/cryptographrix/HooToo_HT-TM05-hacking

## cryptographrix/HooToo_HT-TM05-hacking

### Summary

This repo contains a basic script that downloads the current firmware for the HooToo HT-TM05 portable router and lets you access and modify everything.

## What this actually does

1. Downloads the firmware zip file from the HooToo download site (ZIP)
2. Unzips that into the actual update file, which is a stub of sh and initrdup.gz (UPDATE)
3. Splits the UPDATE file into start_script.sh and initrdup.gz
4. Gunzips initrdup.gz into initrdup
5. Creates ./mount and...
6. Mounts initrdup into ./mount

### QnA

#### Who cares?

Anyone that bought one of these useful portable linux systems and wants to do more with - or customize - it.

#### What can you do from here?

Anything you want - eventually you'll need to reverse the process:

1. sync and unmount initrdup
2. gzip initrdup
3. cat start-script.sh initrdup.gz > fw_...
4. zip fw into HooToo....
