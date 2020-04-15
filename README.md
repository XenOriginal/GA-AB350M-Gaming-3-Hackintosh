# GA-AB350M-Gaming-3-Hackintosh
Hackintosh config for GA-AB350M-Gaming 3

It's perfect on 10.15.4

MotherBoard: GA-AB350M-Gaiming 3

CPU: AMD Ryzen 7 1700

GraphicCard: Radeon Vega Frontier Edition 16 GB

# Caution

Platforminfo

For setting up the SMBIOS info, we'll use CorpNewt's GenSMBIOS and ProperTree application. https://github.com/corpnewt/GenSMBIOS https://github.com/corpnewt/ProperTree

For this example, we'll choose the iMacPro1,1 SMBIOS but some SMBIOS play with certain GPUs better than others:

iMacPro1,1: AMD RX Polaris and newer

MacPro7,1: AMD RX Polaris and newer(Note that MacPro7,1 is also a Catalina exclusive)

MacPro6,1: AMD R5/R7/R9 and older

iMac14,2: Nvidia Kepler and newer

Run GenSMBIOS, pick option 1 for downloading MacSerial and Option 3 for selecting out SMBIOS. This will give us an output similar to the following:

Type:         iMacPro1,1

Serial:       C02YX0TZHX87

Board Serial: C029269024NJG36CB

SmUUID:       DEA17B2D-2F9F-4955-B266-A74C47678AD3

The order is Product | Serial | Board Serial (MLB)

The Type part gets copied to Generic -> SystemProductName.

The Serial part gets copied to Generic -> SystemSerialNumber.

The Board Serial part gets copied to Generic -> MLB.

The SmUUID part gets copied toto Generic -> SystemUUID.

We set Generic -> ROM to either an Apple ROM (dumped from a real Mac), your NIC MAC address, or any random MAC address (could be just 6 random bytes, for this guide we'll use 11223300 0000. After install follow the Fixing iServices page on how to find your real MAC Address)

Reminder that you want either an invalid serial or valid serial numbers but those not in use, you want to get a message back like: "Invalid Serial" or "Purchase Date not Validated"

Apple Check Coverage page https://checkcoverage.apple.com/cn/zh/

# UEFI Setting

Disable:

Fast Boot

VT-d (can be enabled if you set DisableIoMapper to YES)

CSM

Enable:

VT-X

Above 4G decoding

Hyper-Threading

Execute Disable Bit

EHCI/XHCI Hand-off

OS type: Windows 8.1/10 UEFI Mode
