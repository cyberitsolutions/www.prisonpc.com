---
title: 'PILS Device Requirements Desktop Profile'
date: 2024-07-22T17:38:09+10:00
draft: false
url: pils-device-requirements-desktop-pr
---

##### Mandatory Requirements

1. 55cm (21") or larger display.
2. All-in-One chassis.
3. USB ports, for HID devices (e.g. keyboard and mouse).
4. GigE NIC with support for PXE (netboot) and WOL (Wake-on-LAN).
5. x86–64 CPU, although low-end is sufficient.
6. 8G or more of RAM.
7. Glass fascia. Vendors are encouraged to consider the option of stronger tempered glass as some correctional facilities consider this a valuable feature.
8. Internal PSU. An external PSU is not suitable as it can be used as a flail weapon.
9. Chassis secured with Tamper-Resistant Torx (also known as Torx TR) or pin-in Torx to ensure prisoners can not gain access to the internal components.
10. Internal speakers.
11. 3.5mm TRS stereo jack and TS mic, or combined TRRS audio jack.
12. No webcam. Exceptions may be made for desktops isolated in monitored rooms, such as for virtual hearings or similar.
13. No internal storage (HDD, SSD, etc).
14. No wireless communications devices (TV receiver, WiFi, Bluetooth, InfraRed, cellular modem, etc).
15. No microphone.
16. All firmware config screens disabled. It is acceptable for the firmware to only display information such as the date and time, MAC address, etc. Users must not be able to edit any firmware values.
17. Firmware password protection disabled. Note that common 'password protection' is insufficient to satisfy the previous requirement.
18. PrisonPC does not currently support secure boot, but will in future. When it does, secure boot must be configured to include only Cyber IT Solutions' public key in trusted keyring (db), and Microsoft's keys explicitly blacklisted (dbx). Cyber IT Solutions' public key will be available on request.
19. Permit boot from only PXE (netboot).
20. Boot must be disabled from internal storage (HDD, SSD, etc) and removable media (USB, CD/DVD, etc) under all circumstances.
21. WoL (wake-on-LAN) enabled.
22. Any firmware factory default, optimised default, or similar settings, must conform to these requirements. Rationale is to ensure users can't reset to insecure settings.
23. Firmware must not allow updates to be applied by removable media. Any firmware updates can be applied by Cyber IT Solutions over the network via PXE (netboot).

###### Valuable (non-mandatory) Features

1. No accessible mass storage slots (e.g. SD-Card reader), excepting the mandatory USB ports for HID devices. It is sufficient to leave any such device disconnected from the controller.
2. Intel NIC and Intel GPU, as these are most compatible with PrisonPC.
3. Touchscreen. Vendors are encouraged to offer an optional touchscreen interface as some correctional facilities may consider this a valuable feature.
4. Optical (CD/DVD) drive. Some correctional facilities require optical drives while the policy in others is the drive be removed and a blanking plate securely installed in its place.
5. Transparent chassis, with suitable electromagnetic shielding. High-security facilities may appreciate the option of a transparent chassis.
