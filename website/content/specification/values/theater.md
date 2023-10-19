---
title: "Theatre"
---

# Theatre Values

The Theatre or Attack Theater is the area or place from which an attack must occur. Each separate theater represents varying levels of implied trust and attack surface.

## Values

Items that are indented represent more specific values that can be used to describe the parent value. For instance, choosing `Internet` as a value would imply `Remote` as well.

- **Remote**:  The exploit scenario requires that the attack occurs over the network stack; normally external to the target’s internal network such as from the Internet. Common targets in the remote theater are public websites, Domain Name System (DNS) services, or web-browsers.
  - **Internet**:  An attack is able to originate over the internet.
  - **Intranet**:  The attack must be launched from within an organizations internal network that is shielded from direct access of the Internet. (Ex: A router is configured by default to only allow connections from the Intranet ports and not the WAN ports.) This also represents broadcast domains.
  - **Local network**:  An attacker must have access to a physical interface to the network, or collision domain.
- **Limited Remote**:  The exploit scenario requires that the attack can occur over layer 2 or layer 3 technologies, but a limitation exists either by the nature of the network communication or by range constraints.
  - **Bluetooth**:  The attack must be launched relying on a Bluetooth communication channel.
  - **Cellular**:  The attack must be launched from a cellular network.
  - **Infrared**:  The attack must be launched relying on an Infrared communication channel.
  - **Line of Sight**:  The attack must be launched using a Line-of-Sight system such as ocular.
  - **Satellite**:  The attack must be launched using Satellite communication channels.
  - **Wireless**:  The attack must be launched from a wireless (802.11x) network.
- **Local**:  The exploit scenario requires that the attack can only occur after the adversary has logical local access to a device such as through a console, Remote Desktop Protocol (RDP), Secure Shell (SSH), or Telnet login.
- **Physical**:  The exploit scenario requires the attacker’s physical presence at the target.

## Graph View

![Theatre Graph](/figures/graphsnippets/TheatreSnippet.png "Theatre Graph")
