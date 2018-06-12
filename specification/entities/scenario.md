# Scenario Entity

An identifier for another known Vulnerability that can be used in conjunction with the Vulnerability in question to achieve a different and likely greater impact.

## Attributes

### The number attribute

A scenario is the placeholder to allow a description of the conditions surrounding the possible use of a vulnerability. Vulnerability must have a least one Scenario, with multiple possible Scenarios being common. A single Vulnerability can likely be exploited by many different approaches with possible varying impacts. For example, a remote exploit could rely on user interaction to be downloaded whilst a local attacker could use the same vulnerability to obtain the same or similar impact.

Data elements:
- value:  (required) A unique numerical identifier for a given Scenario of the Vulnerability.

Example:
```
value: 1
```
## Relationships

* Attack Theatre: One and only one [Attack Theater](attack-theatre.md) value shall be associated with a Scenario number.

* Vulnerability Type: Zero or many [Vulnerability Type](vulnerability-type.md) values should be associated with a Scenario number. 

* Product: One or many [Product](product.md) values shall be associated with a Scenario number.

* Mitigation: Zero or many [Mitigation](mitigation.md) values should be associated with a Scenario number.

* Barriers:  Zero or many [Barrier](barrier.md) values should be associated with a Scenario number.

* Context:  One or many [Context](context.md) values shall be associated with a Scenario number.