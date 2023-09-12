---
title: "Action"
---

# Action Object

An Action is what occurs within a given Scenario. Actions involve a high level impact method which occur in a specific context. Actions can result in impacts to the context referenced. If multiple contexts are affected there will be multiple actions each relating to a given context.

## Properties

- **id** (one): A globally unique identifier for the action that distinguishes it from other actions related to the same vulnerability.
- **hasName** (zero or one): A name or label to assist in identifying a given action in the context of the containing Vulnerability. This name should be unique across all sibling actions.
- **affectsContext** (one): The conceptual entity where the impacts are realized from successful exploitation of a security vulnerability. Different impacts can be realized by multiple contexts from multiple scenarios. (See [Context](../../values/context))
- **hasEntityRole** (one): Describes the role an associated Context performs in the Vulnerability Scenario Action being described. (See [Entity Role](../../values/entity-role))

## Relationships

- **hasImpactMethod** (one or many): A description of the method used to exploit a vulnerability providing some additional information on the impact of exploitation. (See [Impact Method](../impact-method))
- **resultsInImpact** (one or many): [Impacts](../impact) will occur due to an Action. 
- **doesNotResultInImpact** (zero or many): [Impacts](../impact) will not occur due to an Action.

## Graph View
![Action Graph](/figures/graphsnippets/ActionSnippet.png "Action Graph")