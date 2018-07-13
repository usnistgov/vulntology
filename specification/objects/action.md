# Action Object

An Action is what occurs within a given Scenario. Actions involve a high level impact method which occur in a specific context. Actions can result in impacts to the context referenced. If multiple contexts are affected there will be multiple actions each relating to a given context.

## Properties
- **Impact Method**: Attack Theater is the area or place from which an attack must occur. Each separate theater represents varying levels of implied trust and attack surface. (See [Impact Method Types](../values/impact-method-type.md)) <br />*Each Action has one or many Impact Methods.*
- **Affects Context**: The type, category, or weakness of the Vulnerability. When choosing a value, the most applicable types should be selected based on the type system used. (See [Context Type](../values/context-type.md)) <br />*Each Action has one Affected Context.*
- **Entity Role**: Describes the role an associated Context performs in the Vulnerability Scenario Action being described. (See [Entity Role Type](../values/entity-role-type.md)) <br />*Each Action has one Entity Role.*


## Relationships

* resultsIn: One or many [Impacts](impact.md) will occur due to an Action. 
