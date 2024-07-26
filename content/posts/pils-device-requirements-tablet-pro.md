---
title: 'PILS Device Requirements Tablet Profile'
date: 2024-07-22T17:38:25+10:00
draft: false
url: pils-device-requirements-tablet-pro
---

## Mandatory Requirements

1. 20cm (8") to 25cm (10") display. No particular size in this range is consistently preferred, each facility may have their own preference.
2. Glass fascia. Vendors are encouraged to consider the option of stronger tempered glass as some correctional facilities consider this a valuable feature.
3. Internal PSU, or common USB charging. An external PSU is not suitable as it can be used as a flail weapon.
4. Chassis secured to ensure prisoners can not hide physical contraband, perhaps with [Tamper-Resistant Torx (also known as Torx TR) or pin-in Torx](https://en.wikipedia.org/wiki/Torx).
5. Internal speakers.
6. 3.5mm [TRS stereo jack and TS mic, or combined TRRS audio jack](https://en.wikipedia.org/wiki/Phone_connector_(audio)).
7. Front camera. A rear camera is not necessary, although inclusion of one is acceptable.
8. No TV receiver.
9. No FM receiver.
10. No cellular modem.
11. 2G or more RAM.
12. 2G or more storage.
13. Should support latest release of Google Android (includes GMS) or Google Android Go, although v10+ is acceptable. Earlier versions than v10 are not currently supported by PrisonPC.
14. Must support [Android Enterprise Enrolment](https://www.android.com/intl/en_au/enterprise/enrollment/).
15. Must support [Factory Reset Protection](https://www.samsung.com/nz/support/mobile-devices/what-is-google-frp/).

### Valuable (non-mandatory) Features

1. No accessible mass storage slots (e.g. SD-Card reader), excepting the mandatory USB ports for HID devices or power. To reduce manufacturing complexity and cost it is acceptable to include these connectors but leave the device disconnected from the controller.
2. Transparent chassis, with [suitable electromagnetic shielding](https://en.wikipedia.org/wiki/Electromagnetic_compatibility). For high-security facilities, vendors are encouraged to consider an optional transparent chassis.
3. For charging, USB-C charging is highly recommended as it less prone to damage than micro or mini USB.
4. Hardened chassis. It is important that any custom chassis does not permit users to hide physical contraband.
5. An optional silicone skin, instead of a hardened chassis, for shock protection. Some customers are willing to wear the manual effort required for physical contraband searches.
6. Tablet rear hand holder.
7. [Zero-touch enrolment](https://support.google.com/work/android/answer/7514005?hl=en) may be valuable for some correctional facilities, especially those with a considerable number of tablets.
8. [Android Verified Boot](https://source.android.com/security/verifiedboot) (AVB is common in the majority of CoTS tablet devices).

- AVB implementation must include [rollback protection](https://source.android.com/security/verifiedboot/verified-boot#rollback-protection).
- Must not boot if the AVB verification failed at boot time.
