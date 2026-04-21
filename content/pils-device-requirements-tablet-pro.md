---
date: "2024-07-22T17:38:25+10:00"
draft: false
title: PILS Device Requirements Tablet Profile
description: A list of the requirements a Prisoner Interactive Learning System (PILS) hand-held tablet is required to meet
summary: A list of the requirements a Prisoner Interactive Learning System (PILS) hand-held tablet is required to meet
url: pils-device-requirements-tablet-pro
images:
-
---

> The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://datatracker.ietf.org/doc/html/rfc2119).

## Mandatory requirements

1. 20cm (8") to 25cm (10") display. No particular size in this range is consistently preferred; each facility may have their own preference.
2. Glass fascia. Vendors are encouraged to consider the option of stronger tempered glass as some correctional facilities consider this a valuable feature.
3. Internal PSU, or common USB charging. An external PSU is not suitable as it can be used as a flail weapon.
4. Chassis secured to ensure inmates cannot hide physical contraband, perhaps with [Tamper-Resistant Torx (also known as Torx TR) or pin-in Torx](https://en.wikipedia.org/wiki/Torx).
5. Internal speakers.
6. 3.5mm [TRS stereo jack and TS mic, or combined TRRS audio jack](https://en.wikipedia.org/wiki/Phone_connector_(audio)).
7. Front camera. A rear camera is not necessary, although inclusion of one is acceptable.
8. No TV receiver.
9. No FM receiver.
10. No cellular modem.
11. 2G or more RAM.
12. 2G or more storage.
13. SHOULD support the latest LTS release of Google Chrome OS.
14. MUST support [Chrome Enterprise Enrolment](https://support.google.com/chrome/a/answer/1360534).
15. MUST support [Factory Reset Protection](https://support.google.com/work/android/answer/14549362).

## Valuable (non-mandatory) features

1. No accessible mass storage slots (e.g. SD-Card reader), excepting USB ports for HID devices or power. To reduce manufacturing complexity and cost it is acceptable to include these connectors but leave the device disconnected from the controller.
2. Transparent chassis, with [suitable electromagnetic shielding](https://en.wikipedia.org/wiki/Electromagnetic_compatibility). For high-security facilities, vendors are encouraged to consider an optional transparent chassis.
3. USB-C charging is highly recommended as it is less prone to damage than micro or mini USB.
4. Hardened chassis. It is important that any custom chassis does not permit inmates to hide physical contraband.
5. An optional silicone skin, instead of a hardened chassis, for shock protection. Some facilities are willing to accept the manual effort required for physical contraband searches.
6. Tablet rear hand holder.
7. [Zero-touch enrolment](https://support.google.com/chrome/a/answer/10130175) may be valuable for some correctional facilities, especially those deploying a considerable number of tablets.
8. [Verified Boot](https://www.chromium.org/chromium-os/chromiumos-design-docs/verified-boot/) (Verified Boot is common in the majority of COTS tablet devices).

- Verified Boot implementation MUST include [rollback protection](https://support.google.com/chrome/a/answer/12569990#norollback&zippy=%2Csome-devices-do-not-support-rollback).
- MUST NOT boot if boot verification fails
