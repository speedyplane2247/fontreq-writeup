# Removal
Removal isn't very easy, as most of the version has an anti-unpayload, but don't.
## This guide contains...
This guide contains the unPayload method disinfector, format guide, as well as a fool anti-malware tools for the FontWare trojan. (Aka FontReq)
## unPayload Method
The unpayload method is a method of installing a modified version of the payload, but a "newer" version that replaces the previous payloads.
### Counter Action: Max Version
Some variants will use the maximum possible integer for the version. This prevents installiation, as then nothing can be "newer" than it, preventing Anti-Malware profiles from working. This can't be easily bypassed, and it works for more stealth variants of this, which contain two profiles - (fontreq.mc & fontreqpayload.mc). fontreq launches a MDM server and installs the payload on a later date.
### Counter Action: Profile Prevention
Most variants (including this base variant I uploaded) contain a script to prevent new profiles from being installed. This is very basic, and since most copy-cat variants that are literally copy & pastes of the base malware, edited in NotePad, you have to set the PreventNewProfiles flag to false, so maybe some variants are changed by security researchers.
### Prevention: MDM Preventor
This method of prevention counter-acts the new payload MC file before it is dropped, using the Version integer. This won't let the payload drop, but you are using the C&C server. Variants can easily just increment its payloadID which prevents this.
### Guide
You can check if the anti-viral profiles will work by downloading one at the bottom of the page. (Visit on your phone, infected with the program)
## Format Method (Requires iTunes)
This is probably your best option, as it lets you keep your data. (Some variants preven this).
### Backing Up
First, you need to turn your phone on in regular one. 

Next, you need to unlock and hit "Backup" in iTunes. Some variants will require a password for this part, so just use '123' or such. When you restore, you need to remember this password. (It is very important)
### Formatting
Next, you need to start your phone in DFU mode.

[DFU Guide] (https://www.theiphonewiki.com/wiki/DFU_Mode)

Once you are in DFU mode, you need to plug back in the device, and verify something comes up in iTunes. If not, you did something wrong. You shouldn't see anything on the screen, but the device is recognized in "Recovery Mode" on iTunes.

Next, you just need to hit "Restore iPhone". This will update and reset your phone to factory defaults. 

Finally, you need to re-setup your iPhone.
### Restoring
Now, you need to restore the backup on your phone. This will re-install your data. If you get a prompt to install a profile, hit NO! This is the virus trying to install from the backup.

## MDM Write-Up
The MDM variant is the worst kind. Not only can it spread to other machines without leaving a trace, but it is completely silent, but can knock out thousands of devices at once just by waiting for a lot of devices to come. For this kind, we can't really predict auto-changing profiles, so only 1 anti-profile is here for 
### Spreading
The profile comes at something, usually bunlded with a fake Cydia installer or something like that.  From there, you can uninstall the app by just clicking onthe 'X' icon on the home screen. But, you can't remove the profile. The profile establishes constant connection to an MDM server, from where it send to contacts among other things without user intervention. I don't have a liftable sample, as the MDM server deletes the profile after its launch, and the dropped payload is VERY malcious, but I can drop the IDs. Anti-Profiles for these will be shown.


com.ransomware.mdmdropped (Trojan) & com.ransomware.mdmdropper (Dropper)

I don't have an IP for the MDM, as it uses noip.
### Payload
The payload is much more destructive than the payload MC I uploaded. I couldn't lift the payload off the server, as I got multiple 401s and password requests.
### Fixing
It is much more difficult to remove this profile, as un-like others, the dropper CAN'T be removed. No password or anything, the only way is profile upgrading, which was patched out in the version I used. Also, it was signed with a certificate as well as encrypted, so I couldn't crack it, nor did I feel like wasting time, as it seemed to only include an MDM server, with a few restrictions. I found the server, but I'm not going to name it.
### Uninstalling
Uninstalling isn't easy, but some patches versions exist, but you generally can't install the patched version over the regular, and keeping a (dormant) trojan is still keeping a trojan, so I wouldn't reccomend going out of your way to download the patched versions.
## Profiles
Here are some profiles that will be helpful.
Malware Profile (Installs Malware - Wild Sample) https://raw.githubusercontent.com/speedyplane2247/ios-malware/master/fontware/fontreq.mobileconfig

### Removal Scripts
Here are some of the removal profiles.

This script uses the MaxVersion int to attempt to force its way through.

https://raw.githubusercontent.com/speedyplane2247/ios-malware/master/fontware/removal/MAXVER-DROP.MOBILECONFIG


The following are simple MainVariant Anti-Trojan Profiles. They won't block any changed configs. Install all of these for maximum safety.

https://raw.githubusercontent.com/speedyplane2247/ios-malware/master/fontware/removal/MDMDROPPED.MOBILECONFIG
https://raw.githubusercontent.com/speedyplane2247/ios-malware/master/fontware/removal/MDMDROPPER.MOBILECONFIG
https://raw.githubusercontent.com/speedyplane2247/ios-malware/master/fontware/removal/mainVariant-REMOVAL.MOBILECONFIG


Here is a sample Anti-Trojan, replace 'com.com.com' with the actual ID.

https://raw.githubusercontent.com/speedyplane2247/ios-malware/master/fontware/removal/antitrojan.mobileconfig
