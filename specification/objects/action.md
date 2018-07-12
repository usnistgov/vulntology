# Action Object

A scenario is the placeholder to allow a description of the conditions surrounding the possible use of a vulnerability. Vulnerability must have a least one Scenario, with multiple possible Scenarios being common. A single Vulnerability can likely be exploited by many different approaches with possible varying impacts. For example, a remote exploit could rely on user interaction to be downloaded whilst a local attacker could use the same vulnerability to obtain the same or similar impact.

## Properties
- **Impact Method**: Attack Theater is the area or place from which an attack must occur. Each separate theater represents varying levels of implied trust and attack surface. (See [Impact Method Types](impact-method-type.md)) <br />*Each Action has one or many Impact Methods.*
- **Affects Context**: The type, category, or weakness of the Vulnerability. When choosing a value, the most applicable types should be selected based on the type system used. (See [Context Type](context-type.md)) <br />*Each Action has one Affected Context.*
- **Entity Role**: Describes the role an associated Context performs in the Vulnerability Scenario Action being described. (See [Entity Role Type](entity-role-type.md)) <br />*Each Action has one Entity Role.*


## Relationships

* resultsIn: One or many [Impacts](impact.md) will occur due to an Action. 