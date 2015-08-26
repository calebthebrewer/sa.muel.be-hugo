+++
date = "2015-08-26T18:55:47+02:00"
title = "The right way to create Windows installation media"

+++

There are several ways to create a USB stick to install Windows. Chances are you end up with an error during the installation or you (unknowingly) use the wrong partition layout for your HDD/SSD.

## Get an ISO

Which version of Windows do you want to install? This guide would work fine with Windows 7 or newer, but you can get an ISO for Windows 10 Home/Pro on [this page](https://www.microsoft.com/en-us/software-download/windows10ISO).

The problem with that page, however, is that it redirects you to a download of a media creation tool if you're opening the page on a Windows PC. The media creation tool allows you to download an ISO image, but it [doesn't always work properly](http://d.ibtimes.co.uk/en/full/1451630/windows-10-installation-errors.png).

So fiddle with your user agent settings (the hard way)...

or open it up on your smartphone, select the version of Windows you want to download and send the direct download to yourself (the easy way).

## Get Rufus

[Rufus](http://rufus.akeo.ie/) is a simple tool which allows you to easily create bootable USB sticks for any kind of operating system. Download it, you don't have to install it.

## Creating the image

Now plug in your USB stick, fire up Rufus and point it to your USB stick (first dropdown list) and the ISO image (button next to the last dropdown list) you just downloaded. Now **pay attention** to the next steps, because Rufus will delete everything on the USB stick/disk you select.

Select *GPT with UEFI* for the partition layout.

Pick *FAT32* as filesystem (no, NTFS will not work).

Leave the cluster size at its default (*4096 bytes*).

Make sure the third checkmark next to *Create bootable disk with ISO image* is checked.

Now all you have to do is press *Start* :)

## Booting the image

This guide ends here, but if you don't know how to boot your PC from the installation image you just created, consult the manual of your PC, BIOS or motherboard. *Usually you need to press one of the F-buttons while the logo of your motherboard's manufacturer is displayed.*