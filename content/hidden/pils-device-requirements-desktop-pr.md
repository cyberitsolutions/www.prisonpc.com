---
date: "2024-07-22T17:38:09+10:00"
draft: false
title: PILS Device Requirements Desktop Profile
description: A list of the requirements a Prisoner Interactive Learning System (PILS) desktop computer is required to meet
url: pils-device-requirements-desktop-pr
images:
-
---

# Hardware Requirements

## Mandatory

1. 55cm (21") or larger display.
1. All-in-One chassis.
1. USB ports, for HID devices (e.g. keyboard and mouse).
1. GigE NIC with support for PXE (netboot) and WOL (Wake-on-LAN).
1. x86–64 CPU, although low-end is sufficient.
1. 8G or more of RAM.
1. Glass fascia. Vendors are encouraged to consider the option of stronger tempered glass as some correctional facilities consider this a valuable feature.
1. Internal PSU. An external PSU is not suitable as it can be used as a flail weapon.
1. Chassis secured with Tamper-Resistant Torx (also known as Torx TR) or pin-in Torx to ensure prisoners can not gain access to the internal components.
1. Internal speakers.
1. 3.5mm TRS stereo jack and TS mic, or combined TRRS audio jack.
1. No webcam. Exceptions may be made for desktops isolated in monitored rooms, such as for virtual hearings or similar.
1. No internal storage (HDD, SSD, etc).
1. No wireless communications devices (TV receiver, WiFi, Bluetooth, InfraRed, cellular modem, etc).
1. No microphone.

## Valuable (non-mandatory) Features

#. No accessible mass storage slots (e.g. SD-Card reader), excepting the mandatory USB ports for HID devices. It is sufficient to leave any such device disconnected from the controller.
#. Intel NIC and Intel GPU, as these are most compatible with PrisonPC.
#. Touchscreen. Vendors are encouraged to offer an optional touchscreen interface as some correctional facilities may consider this a valuable feature.
#. Optical (CD/DVD) drive. Some correctional facilities require optical drives while the policy in others is the drive be removed and a blanking plate securely installed in its place.
#. Transparent chassis, with suitable electromagnetic shielding. High-security facilities may appreciate the option of a transparent chassis.

# Firmware Requirements

## Mandatory BIOS

1. All firmware config screens disabled. It is acceptable for the firmware to only display information such as the date and time, MAC address, etc. Users must not be able to edit any firmware values.
1. Firmware password protection disabled. Note that common 'password protection' is insufficient to satisfy the previous requirement.
1. PrisonPC does not currently support secure boot, but will in future. When it does, secure boot must be configured to include only Cyber IT Solutions' public key in trusted keyring (db), and Microsoft's keys explicitly blacklisted (dbx). Cyber IT Solutions' public key will be available on request.
1. Permit boot from only PXE (netboot).
1. Boot must be disabled from internal storage (HDD, SSD, etc) and removable media (USB, CD/DVD, etc) under all circumstances.
1. WoL (wake-on-LAN) enabled.
1. Any firmware factory default, optimised default, or similar settings, must conform to these requirements. Rationale is to ensure users can't reset to insecure settings.
1. Firmware must not allow updates to be applied by removable media. Any firmware updates can be applied by Cyber IT Solutions over the network via PXE (netboot).

## Mandatory UEFI

The intent of these requirements is to ensure the PILS desktop will boot operating systems signed exclusively by Cyber IT (ie; not by Microsoft etc), and will not allow an attacker/end-user with physical access to undermine the previous points (e.g. by disabling secure boot, e.g. by triggering a "factory reset" of the UEFI settings).

1. CSM ("legacy BIOS mode") must be removed/disabled.
1. Secure Boot must be enabled.
1. The only secure boot "PK" key should be the certificate provided by Cyber IT.
1. The only secure boot "KEK" key must be the certificate provided by Cyber IT.
1. The only secure boot "db" key must be the certificate provided by Cyber IT.

