# Attack Theater Entity

Attack Theater is the area or place from which an attack must occur. Each separate theater represents varying levels of implied trust and attack surface.

## Attributes

### The *theater* attribute

The exploit scenario requires that the attack occurs over the network stack; normally external to the target’s internal network such as from the Internet. Common targets in the remote theater are public websites, Domain Name System (DNS) services, or web-browsers.

**Cardinality**: One

#### Valid values

The theater attribute value must be one of the following values or sub-values. A sub-value implies the parent value:

- **remote**: The exploit scenario requires that the attack occurs over the network stack; normally external to the target’s internal network such as from the Internet. Common targets in the remote theater are public websites, Domain Name System (DNS) services, or web-browsers.
  - **internet**:
  - intranet
  - local network
- limited remote: The exploit scenario requires that the attack can occur over layer 2 or layer 3 technologies, but a limitation exists either by the nature of the network communication or by range constraints. Examples of range constraints are *Cellular*, *Wireless*, *Bluetooth*, *Infrared*, or *Line-Of-Sight*.
  - bluetooth
  - cellular
  - infrared
  - line of sight
  - satellite
  - wireless
- local
- physical

Refined by: Remote Type
 * One and only one Remote Type value should be associated with Remote.

Data elements:
- namespace: (required) The specific grouping of unique identifiers. 
- value: (required) A unique namespace-qualified identifier for the Vulnerability.

Example:
```
namespace: cve.mitre.org
value: CVE-2015-1234
```

## Relationships

* Scenario: One or many [Scenario](scenario.md) values shall be associated with Vulnerability.

* Provenance: One or many [Provenance](provenance.md) values should be associated with Vulnerability. 

* Sector of Interest: Zero or many [Sector of Interest](sector-of-interest.md) values should be associated with Vulnerability. 

* Known Chain: Zero or many [Known Chain](known-chain.md) values should be associated with Vulnerability.
