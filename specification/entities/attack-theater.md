# Attack Theater Entity

Attack Theater is the area or place from which an attack must occur. Each separate theater represents varying levels of implied trust and attack surface.

## Attributes

### The *theater* attribute

**Cardinality**: One

#### Valid values

The theater attribute value must be one of the following values or sub-values. A sub-value implies the parent value:

- **remote**:  The exploit scenario requires that the attack occurs over the network stack; normally external to the target’s internal network such as from the Internet. Common targets in the remote theater are public websites, Domain Name System (DNS) services, or web-browsers.
  - **internet**:  An attack is able to originate over the internet.
  - **intranet**:  The attack must be launched from within an organizations internal network that is shielded from direct access of the Internet. (Ex: A router is configured by default to only allow connections from the Intranet ports and not the WAN ports.) This also represents broadcast domains.
  - **local network**:  An attacker must have access to a physical interface to the network, or collision domain.
- **limited remote**:  The exploit scenario requires that the attack can occur over layer 2 or layer 3 technologies, but a limitation exists either by the nature of the network communication or by range constraints.
  - **bluetooth**:  The attack must be launched relying on a Bluetooth communication channel.
  - **cellular**:  The attack must be launched from a cellular network.
  - **infrared**:  The attack must be launched relying on an Infrared communication channel.
  - **line of sight**:  The attack must be launched using a Line-of-Sight system such as ocular.
  - **satellite**:  The attack must be launched using Satellite communication channels.
  - **wireless**:  The attack must be launched from a wireless (802.11x) network.
- **local**:  The exploit scenario requires that the attack can only occur after the adversary has logical local access to a device such as through a console, Remote Desktop Protocol (RDP), Secure Shell (SSH), or Telnet login.
- **physical**:  The exploit scenario requires the attacker’s physical presence at the target.

Data elements:
- namespace: (required) The specific grouping of unique identifiers. 
- value: (required) A unique namespace-qualified identifier for the Vulnerability.

Example:
```
namespace: vulntology.nist.gov
value: Remote
```
