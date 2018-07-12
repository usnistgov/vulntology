# Scenario Object

A scenario is the placeholder to allow a description of the conditions surrounding the possible use of a vulnerability. Vulnerability must have a least one Scenario, with multiple possible Scenarios being common. A single Vulnerability can likely be exploited by many different approaches with possible varying impacts. For example, a remote exploit could rely on user interaction to be downloaded whilst a local attacker could use the same vulnerability to obtain the same or similar impact.

## Properties
- **Attack Theater**: Attack Theater is the area or place from which an attack must occur. Each separate theater represents varying levels of implied trust and attack surface. (See [Attack Theater Types](attack-theater.md)) <br />*Each Scenario has one Attack Theatre.*
- **Vulnerability Type**: The type, category, or weakness of the Vulnerability. When choosing a value, the most applicable types should be selected based on the type system used. (See [Vulnerability Types](vulnerability-type.md)) <br />*Each Scenario has one Vulnerability Type.*


## Relationships

* provenBy: One or many [Provenance](provenance.md) will assist in proving a Vulnerability Scenario is legitimate. 

* affectsProduct: One or many [Products](product.md) will be affected within a Scenario.

* blockedBy: Zero or many [Barriers](barrier.md) may increase the difficulty of a Scenario.

* hasAction: One or many [Actions](action.md) will occur within a Scenario