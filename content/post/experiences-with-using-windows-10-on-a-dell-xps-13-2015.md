+++
date = "2015-08-24T07:40:34+02:00"
draft = true
title = "Experiences with using Windows 10 on a Dell XPS 13 (2015)"

+++

## Ordering a new workhorse

Windows 10 RTM has been out for about a month now after little less than a year of public Insider preview builds. The motherboard of my old, trusty, Asus laptop was slowly dying and the Dell XPS 13's thinness and battery life looked very attractive. I decided to go for it and order a Dell XPS 13 (2015), without the touch screen. I hate dirty fingerprints on a screen and the better battery life of the version without the touch screen seemed like a better deal. I also ordered a USB 3 -> HDMI/VGA/ethernet/USB 2 adapter from Dell.

While Dell's website tells you they will ship it in about 4 business days, it took nearly 3 weeks until UPS rang my bell with a shipment from China. By the way, Dell Belgium's sales support is terrible. They offer support by phone and chat, but they will tell you on both channels that you have to send them an email. The Belgian support department was very abrupt and impolite. They can't tell you why it looks like your laptop is sitting in an UPS storage facility in China without moving for about a week.

## First steps

The first thing I did after unpacking everything, was booting it up and installing DriveImage XML to create a complete image of every partition so it would be easy to restore if something ever went terribly wrong (we all heard the Windows 10 'Something happened' installation horror stories). Windows also comes with a tool to create system recovery images on USB sticks etc. This tool copies the recovery partition to a USB stick, together with Windows recovery tools.

On a side note: a lot of programs like DriveImage XML looked very blurry on the XPS 13's 1080p screen.

## So many Windows 10s!

If I'd simply upgrade the Windows 8.1 installation that shipped with the XPS 13, I'd get the most basic version of Windows 10. This would simply not suffice for most software developers. I signed in to Microsoft Dreamspark and got the free Windows 10 Education I'm entitled to as an IT student. I had the choice of installing the Enterprise or the Education edition. The Education edition comes with more features and I figured the Enterprise edition wouldn't be as easy to install outside a domain.

I rebooted the machine with the Windows 10 installation media and deleted every parition on the SSD. After the installation, Windows 10 guides you through the final steps of setting up your new PC.

Usually, they ask you to sign in to a Microsoft account and offer you to restore the apps and settings from another machine on which you're signed in. Apparently that's not the case if you picked the Education edition: sign in with a domain account or create a local user account. I could link my local account to a Microsoft account after the initial setup, but my desktop now shows a white watermark in the bottom right corner saying *Windows 10 Education* (which is impossible to remove without changing some HEX values in the registry...)

## The first boot

The blurryness was back. Every non-modern app was back. Probably driver issues, right? Dell's support site says that the XPS 13 is ready for Windows 10. Okay... But the driver section doesn't even have a graphics driver. I installed all the available Windows 10 drivers and some Windows 8 drivers which weren't available in the Windows 10 section. I found drivers for the Intel HD 5500 and some other Intel components on Intel's website and Realtek's website has Windows 10 drivers for SD card reader and the audio chip.

The installation of the graphics driver failed miserably. In the final step of the installation my screen turned black, showing just a white mouse pointer. It stayed that way for more than 15 minutes. Although, after a reboot (had to press the power button for a few seconds), the driver seemed to be *correctly* installed.

The installation of the audio driver just failed completely. The first step of the installation uninstalls your existing driver and asks you to reboot. The second step should install the new driver, but after a reboot the installation process rebegan. I stopped trying after 4 attempts as audio seemed to be working fine.

## The blurryness (is here to stay)

It was still there. I fiddled a little bit with the Intel HD Graphics Control Panel and enabled some settings that should improve the quality of textures. That was a bad choice. If you enable most settings in the *3D* section of the control panel, textures in modern apps will look very dark and the Windows 10 start menu becomes one dark grey mess. **Disable all settings in the *3D* section of the Intel HD Graphics Control Panel on Windows 10**.

My next try was ClearType. This helped a little bit with the blurryness, but not that much.

Finally, I played with the DPI scaling. The factory default is 150%. I found that 125% is not too blurry and not too small. I'd prefer a non-blurry screen on 150% scaling though.

I concluded that most Windows applications simply aren't built with high DPI screens in mind. It's the retina story of the new Macs all over again.

## Some issues I worked around or fixed

### The failing touchpad driver update

Windows 10 tried to install an update for the touchpad driver and kept on failing. This was a known issue you could safely ignore. Microsoft offers a utility to hide some specific updates.

### The Dell adapter

Installing and plugging in the Dell adapter I bought, gave me BSoDs and a lot of other crap. Installing a recent driver from DisplayLink, its manufacturer, fixed it.

### Distorted sound

Sometimes the audio driver went berserk and the sound became very distorted. Disabling and enabling the Realtek HW audio codec usually fixed it temporarily, but it was finally fixed after installing a new version of the Realtek audio driver last week.

### Missing settings in the power management section of the control panel

Dell offers a great utility called *Dell Command | Power* which you should definitely install if you own a recent Dell laptop. You can optimize various settings that avoid battery wear.

You can also use this trick to enable some settings in the control panel that were hidden by the manufacturer of your device.

### Slow wi-fi

The latest version of the wi-fi driver that's available on Intel's website fixed an issue where I would experience a very slow wi-fi connectioon from time to time.

## A quick review

### The battery life

Dell promises 10+ hours of battery life with this laptop. I never even got close. You'd probably only get this with your laptop on the lowest brightness setting in flight mode. I usually get up to 8 hours with light usage (browsing, reading...) and up to 4 hours with heavy usage (running multiple instances of Visual Studio and building about every 15 minutes).

I'm quite happy with the battery life, it's not as good as expected, but still a lot better than what you get from most other (non-Apple) laptops.

### The screen

Software developers need to start thinking about high DPI screens. I didn't even get the 4K screen. I love the thin bezels and the screen looks very good except in direct sunlight.

### The touch pad

I highly recommend playing a little bit with the settings. A lot of people seem to be complaining about some kind of lag or delay. You can adjust this delay in the settings. I've put it on the shortest delay, but haven't disabled the delay completely.

The touch pad works fine, it registers everything I want it to.

### The keyboard

The keys are very thin and but typing is quite comfortable. The backspace and the FN buttons are placed awkwardly (especially if you use multiple desktops in Windows 10), but I got used to it.

### Performance

The performance really depends on the configuration you pick. I picked the Intel i7-5600U with 8 GB of RAM. I would have loved a 16 GB configuration and all you can upgrade is the SSD. It isn't as fast as the quad core i7 with Hyper Threading I used to have, but the difference is hardly noticeable.

## Conclusion

