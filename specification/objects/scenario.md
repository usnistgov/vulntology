# Scenario Object

A scenario describes the conditions surrounding the possible use of a vulnerability. A Vulnerability must have a least one Scenario, with multiple possible Scenarios being common. A single Vulnerability can likely be exploited by many different approaches with possible varying impacts. Multiple Scenarios can be used to describe these variations. For example, a remote exploit could rely on user interaction to be downloaded whilst a local attacker could use the same vulnerability to obtain the same or similar impact.

## Properties
- **id** (one): A globally unique identifier for the scenario that distinguishes it from other scenarios related to the same vulnerability.
- **hasName** (zero or one): A name or label to assist in identifying a given scenario in the context of the containing Vulnerability. This name should be unique across all sibling scenarios.
- **requiresAttackTheater** (one): Attack Theater is the area or place from which an attack must occur. Each separate theater represents varying levels of implied trust and attack surface. (See [Theater](../values/theater.md))
- **evidencedBySource** (one or many):  [Resource Reference](../values/resource-reference.md) will assist in proving a Vulnerability Scenario is legitimate. 
- **hasExploitedWeakness** (one): The weakness causing the Vulnerability. When choosing a value, the most applicable weakness should be selected. (See [Exploited Weakness](../values/exploited-weakness.md))


## Relationships

- **affectsProduct** (one): [Products](product.md) identify the set of products affected within a Scenario.

- **blockedByBarrier** (zero or many): [Barriers](barrier.md) may increase the difficulty of a Scenario.

- **hasAction** (one or many): [Actions](action.md) will occur within a Scenario

![Scenario Graph](../figures/graphsnippets/ScenarioSnippet.png "Scenario Graph")