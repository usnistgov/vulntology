---
title: "Scenario"
---

# Scenario Object

A scenario describes the conditions surrounding the possible use of a vulnerability. A Vulnerability must have a least one Scenario, with multiple possible Scenarios being common. A single Vulnerability can likely be exploited by many different approaches with possible varying impacts. Multiple Scenarios can be used to describe these variations. For example, a remote exploit could rely on user interaction to be downloaded whilst a local attacker could use the same vulnerability to obtain the same or similar impact.

## Properties

An *scenario* has the following properties.

### Identifier

{{%usa-tag%}}Name{{%/usa-tag%}} `id`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} A globally unique identifier for the *scenario*.

The action identifier distinguishes the *scenario* from other *scenarios* related to the same *vulnerability*.

This identifier MUST be a version 4 (random) or 5 (SHA-1 based) Universally Unique Identifier (UUID) as defined by [RFC 4122](https://www.rfc-editor.org/rfc/inline-errata/rfc4122.html).

### Name

{{%usa-tag%}}Name{{%/usa-tag%}} `hasName`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} zero or one
{{%usa-tag%}}Description{{%/usa-tag%}} A name or label to assist in identifying a given *scenario* in the context of the containing *vulnerability*.

A given *scenario* name MUST be unique across all sibling *scenarios*.

The value of `hasName` MUST be based on the lexical space of a string as defined by [ECMA-404 2nd edition, section 9](https://www.ecma-international.org/wp-content/uploads/ECMA-404_2nd_edition_december_2017.pdf).

### Attack Theater

{{%usa-tag%}}Name{{%/usa-tag%}} `requiresAttackTheater`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} Attack Theater is the area or place from which an attack must occur.

Each separate theater represents varying levels of implied trust and attack surface.

The value of `requiresAttackTheater` MUST be a value from the [theater value list](../../values/theater).

### Evidence Source

{{%usa-tag%}}Name{{%/usa-tag%}} `evidencedBySource`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one or many
{{%usa-tag%}}Description{{%/usa-tag%}} A *resource reference* that will assist in supporting the existence of a *vulnerability* *scenario*.

The value of `evidencedBySource` MUST be a [resource value](../../values/resource-reference).

### Exploited Weakness

{{%usa-tag%}}Name{{%/usa-tag%}} `hasExploitedWeakness`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} The weakness causing the *vulnerability*.

When choosing a value, the most applicable weakness should be selected. (See [Exploited Weakness](../../values/exploited-weakness))

The value of `hasExploitedWeakness` MUST be an [exploited weakness value](../../values/exploited-weakness).

## Relationships

A *scenario* has the following relationships.

### Affected Product

{{%usa-tag%}}Name{{%/usa-tag%}} `affectsProduct`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} Identifies the set of *products* affected within a *scenario*.

The object value of the `affectsProduct` relationship MUST be a [*product*](../product) object.

### Blocked By Barrier

{{%usa-tag%}}Name{{%/usa-tag%}} `blockedByBarrier`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} zero or many
{{%usa-tag%}}Description{{%/usa-tag%}} Describes a characteristic inherent in the *vulnerability* that may increase the difficulty of exploiting a *scenario*.

The object value of the `blockedByBarrier` relationship MUST be a [*barrier*](../barrier) object.

### Action

{{%usa-tag%}}Name{{%/usa-tag%}} `hasAction`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one or many
{{%usa-tag%}}Description{{%/usa-tag%}} [Actions](../action) will occur within a Scenario

The object value of the `hasAction` relationship MUST be a [*action*](../action) object.

## Example
```json
{
 "hasScenario": [
    {
     "id": "S1",
     "requiresAttackTheatre": "Remote::Internet",
     "hasExploitedWeakness": ["CWE-79"],
     "evidencedBySource": ["https://www.acme.com"],
     "affectsProduct": {
        },
     "blockedByBarrier": [
        ],
     "hasAction": [
        ]
    },
 ]
}
```

## Graph View

![Scenario Graph](/figures/graphsnippets/ScenarioSnippet.png "Scenario Graph")
