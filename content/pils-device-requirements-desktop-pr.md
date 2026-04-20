---
date: "2024-07-22T17:38:09+10:00"
draft: false
title: PILS Device Requirements Desktop Profile
description: A list of the requirements a Prisoner Interactive Learning System (PILS) desktop computer is required to meet
url: pils-device-requirements-desktop-pr
images:
-
---

> The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://datatracker.ietf.org/doc/html/rfc2119).

## Mandatory hardware requirements

1. 55cm (21") or larger display.
1. All-in-One chassis.
1. USB ports, for HID devices (e.g. keyboard and mouse).
1. GigE NIC with support for PXE (netboot) and WOL (Wake-on-LAN).
1. x86-64 CPU, although low-end is sufficient.
1. 8G or more of RAM.
1. Glass fascia. Vendors are encouraged to consider the option of stronger tempered glass as some correctional facilities consider this a valuable feature.
1. Internal PSU. An external PSU is not suitable as it can be used as a flail weapon.
1. Chassis secured with Tamper-Resistant Torx (also known as Torx TR) or pin-in Torx to ensure inmates cannot gain access to the internal components.
1. Internal speakers.
1. 3.5mm TRS stereo jack and TS mic, or combined TRRS audio jack.
1. No webcam. Exceptions may be made for desktops isolated in monitored rooms, such as for virtual hearings or similar.
1. No internal storage (HDD, SSD, etc).
1. No wireless communications devices (TV receiver, WiFi, Bluetooth, InfraRed, cellular modem, etc).
1. No microphone.

## Valuable (non-mandatory) hardware attributes

1. No accessible mass storage slots (e.g. SD-Card reader), excepting the mandatory USB ports for HID devices. It is sufficient to leave any such device disconnected from the controller.
1. Intel NIC and Intel GPU, as these are most compatible with PrisonPC.
1. Touchscreen. Vendors are encouraged to offer an optional touchscreen interface as some correctional facilities may consider this a valuable feature.
1. Optical (CD/DVD) drive. Some correctional facilities require optical drives while the policy in others is that the drive be removed and a blanking plate securely installed in its place.
1. Transparent chassis, with suitable electromagnetic shielding. High-security facilities may appreciate the option of a transparent chassis.

## Mandatory firmware requirements

The Legacy BIOS requirements below can only be implemented by the desktop hardware manufacturer, as the necessary customisations are not accessible post-manufacture. The UEFI requirements may be applied by a suitably experienced system integrator or consultant as UEFI and secure boot configuration is typically accessible during the integration and deployment process.

### Legacy BIOS

PrisonPC supports both legacy BIOS and UEFI firmware, allowing deployment on older or recycled hardware that may not include full UEFI support. While UEFI with secure boot is strongly preferred for new hardware purchases, legacy BIOS hardware remains a viable and supported option where budget or hardware availability constraints apply. The requirements below apply specifically to legacy BIOS devices.

1. All firmware config screens disabled. It is acceptable for the firmware to only display information such as the date and time, MAC address, etc. Users MUST NOT be able to edit any firmware values.
1. Firmware password protection disabled. Note that common password protection is insufficient to satisfy the previous requirement.
1. Permit boot from only PXE (netboot).
1. Boot MUST be disabled from internal storage (HDD, SSD, etc) and removable media (USB, CD/DVD, etc) under all circumstances.
1. WoL (wake-on-LAN) enabled.
1. Any firmware factory default, optimised default, or similar settings, MUST conform to these requirements. Rationale is to ensure users cannot reset to insecure settings.
1. Firmware MUST NOT allow updates to be applied by removable media. Any firmware updates can be applied by PrisonPC over the network via PXE (netboot).

### UEFI

The intent of these requirements is to ensure the PILS desktop will boot operating systems signed exclusively by PrisonPC (not by Microsoft etc), and will not allow an attacker or end-user with physical access to undermine the previous points (e.g. by disabling secure boot, or by triggering a factory reset of the UEFI settings).

1. CSM ("legacy BIOS mode") MUST be removed/disabled.
1. Secure Boot MUST be enabled.
1. The only secure boot "PK" key SHOULD be the certificate provided by PrisonPC.
1. The only secure boot "KEK" key MUST be the certificate provided by PrisonPC.
1. The only secure boot "db" key MUST be the certificate provided by PrisonPC.
1. The secure boot "KEK" and "db" keyrings MUST NOT include any of these certificates:
   - <https://gitlab.com/kraxel/virt-firmware/-/tree/v24.2/virt/firmware/certs>
   - <https://gitlab.com/kraxel/virt-firmware/-/tree/master/virt/firmware/certs>
1. The secure boot "dbx" keyring MUST NOT include the certificate provided by PrisonPC.
1. The secure boot "dbx" keyring MAY include some/all of these certificates:
   - <https://gitlab.com/kraxel/virt-firmware/-/tree/v24.2/virt/firmware/certs>
   - <https://gitlab.com/kraxel/virt-firmware/-/tree/master/virt/firmware/certs>
1. The UEFI config (e.g. "hit F2/Del during boot") MUST NOT allow the end user to change or bypass any of the above-mentioned settings in any way.
1. Triggering a factory reset condition MUST NOT allow the end user to change or bypass any of the above-mentioned settings in any way, e.g. by opening the case and shorting a jumper, or by toggling the power switch in quick succession thus triggering a hardware reset.
1. Network boot MUST be possible (e.g. DHCPv4 + TFTP, or DHCPv4 + HTTP).

