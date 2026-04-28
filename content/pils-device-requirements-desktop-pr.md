---
date: "2024-07-22T17:38:09+10:00"
draft: false
title: PILS Device Requirements Desktop Profile
description: A list of the requirements a Prisoner Interactive Learning System (PILS) desktop computer is required to meet
url: pils-device-requirements-desktop-pr
images:
-
---

# PrisonPC Requirements

The following requirements cover both hardware and firmware. PrisonPC supports both Legacy BIOS and UEFI firmware, allowing deployment on older or recycled hardware that may not include full UEFI support. UEFI with Secure Boot is strongly preferred for new hardware purchases, however the firmware requirements below apply to whichever firmware mode the device supports. For UEFI devices, the intent is to ensure the PILS desktop will boot operating systems signed exclusively by PrisonPC (not by Microsoft or similar), and that an attacker or end-user with physical access cannot undermine this (e.g. by disabling Secure Boot or triggering a factory reset of the UEFI settings).

> The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://datatracker.ietf.org/doc/html/rfc2119).

1. SHOULD include Intel NIC and Intel GPU, as these are most compatible with PrisonPC.
1. MUST include GigE speed NIC.
1. NIC MUST support PXE (netboot)
1. NIC SHOULD support WOL (Wake-on-LAN).
1. CPU MUST be x86-64 (i.e., not ARM), and MAY be low-end/low-speed.
1. MUST include 8G+ RAM.
1. UEFI SHOULD be used for new hardware purchases
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
1. Legacy BIOS MAY be used where budget or hardware constraints apply
   1. Firmware configuration screens MUST be disabled. It is acceptable for the firmware to display read-only information such as date, time, and MAC address, but users MUST NOT be able to edit any firmware values.
   1. Firmware password protection MUST be disabled. Note that common password protection is insufficient to satisfy the previous requirement.
   1. The device MUST boot from PXE (netboot) only.
   1. Boot from internal storage (HDD, SSD, etc) and removable media (USB, CD/DVD, etc) MUST be disabled under all circumstances.
   1. WoL (Wake-on-LAN) SHOULD be enabled.
   1. Any firmware factory default, optimised default, or similar reset condition MUST conform to these requirements, to ensure users cannot reset to insecure settings.
   1. Firmware MUST NOT permit updates to be applied via removable media. Firmware updates MAY be applied by PrisonPC over the network via PXE (netboot).

# Correctional Facility Requirements

We have observed, across many correctional facility deployments, that procuring facilities commonly specify requirements beyond those mandated by PrisonPC itself. These are not requirements of the PrisonPC platform; a device meeting only the PrisonPC requirements above will function correctly. They are included here because vendors who anticipate these preferences will be better positioned to meet tender requirements.

1. 55cm (21") or larger display.
1. All-in-One chassis.
1. USB ports, for HID devices (e.g. keyboard and mouse).
1. Glass fascia. Vendors are encouraged to consider the option of stronger tempered glass as some correctional facilities consider this a valuable feature.
1. Internal PSU. An external PSU is not suitable as it can be used as a flail weapon.
1. No webcam. Exceptions may be made for desktops isolated in monitored rooms, such as for virtual hearings or similar.
1. No internal storage (HDD, SSD, etc).
1. No wireless communications devices (TV receiver, WiFi, Bluetooth, InfraRed, cellular modem, etc).
1. No microphone.
1. No accessible mass storage slots (e.g. SD-Card reader), excepting the mandatory USB ports for HID devices. It is sufficient to leave any such device disconnected from the controller.
1. Chassis secured with Tamper-Resistant Torx (also known as Torx TR) or pin-in Torx to ensure inmates cannot gain access to the internal components.
1. Internal speakers.
1. 3.5mm TRS stereo jack and TS mic, or combined TRRS audio jack.
1. Optical (CD/DVD) drive. Some correctional facilities require optical drives while the policy in others is that the drive be removed and a blanking plate securely installed in its place.
1. Transparent chassis, with suitable electromagnetic shielding. High-security facilities may appreciate the option of a transparent chassis.
1. Touchscreen interface.

