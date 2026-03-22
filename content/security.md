---
date: "2024-07-19T13:50:32+10:00"
draft: false
images:
- images/security-header.webp
title: Hardened Security
description: "PrisonPC is designed from the ground up with security as its foundation; a multi-layered, default-deny architecture built specifically for the correctional environment."
url: /security
---

PrisonPC employs a [multi-layered default-deny](https://en.wikipedia.org/wiki/Defense_in_depth_(computing)) security policy throughout. Each layer is designed to operate independently, so that if one mechanism is bypassed, the layers beneath it continue to protect the system. No single point of failure exposes the facility to risk.

The security architecture covers the full stack: desktop hardware, physical peripherals, server infrastructure, network topology, device connectivity, and media access. Each is addressed by design, not by policy alone.

## Desktop security

PrisonPC desktops contain no writable storage; no hard drive, no USB storage, no writable optical media. The operating environment is read-only and immutable. Inmates cannot install software, modify system configuration, or persist any changes across sessions. The desktop state is identical at every login.

This architecture makes the desktops inherently resistant to malware, keyloggers, spyware, and any attempt at unauthorised software installation; not because of antivirus software, but because there is nothing to write to.

## Physical security

All-in-One desktop computers are recommended for correctional deployments. The consolidated chassis significantly reduces the voids and removable components that separate tower systems offer for contraband concealment.

The PrisonPC peripheral kit (keyboard, mouse, network cable, headphones, power and audio cables) is designed with staff and inmate safety as the primary consideration. All cables are 30cm in length, reducing ligature risk. The keyboard and mouse are compact and lightweight, reducing their utility as improvised weapons.

## Server security

Each inmate's file storage is isolated on the servers, accessible only to that inmate and to authorised staff. Inmates cannot access each other's data, and no shared storage exists that could be used to pass files between users.

Staff retain full visibility and access to all inmate storage. Archival snapshots with a managed retention policy additionally allow staff to access files that have since been deleted by inmates.

## Network security

The management console is protected against intrusion from unauthorised users and unauthorised network locations. All system authentication is encrypted in transit. The inmate network and the staff network are architecturally separated; staff systems are not reachable from inmate desktops under any circumstances.

## Device and media security

PrisonPC operates on an explicit allow-list model for connected devices. Any device not on the approved list (USB storage, mobile broadband adaptors, WiFi controllers, webcams, Bluetooth transceivers) is rejected at connection and triggers an immediate staff alert. This is enforced through software policy rather than hardware customisation, with the exception of insecure components such as hard drives and webcams which are physically removed from desktops prior to deployment.

Optical media follows the same model. Inmates can only access discs that have been explicitly approved by staff for inmate use. Any attempt to use unapproved media triggers a staff alert.

## Event logging and monitoring

All user sessions are logged in full. Staff can review session logs retrospectively, monitor desktops in real time, broadcast alerts to individual or groups of users, and remotely control or shut down any desktop without physical access to the cell.

> "Security best practices aren't aspirational goals, they're the baseline of professional competence. They aren't the ceiling you reach for, they're the floor you stand on."
>
> — Barry Anderson, Security Architect, Cisco Systems
