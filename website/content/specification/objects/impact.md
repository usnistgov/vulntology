---
title: "Impact"
---

# Impact Object

An *impact* is a recognized result of an [*action*](../action) taken for a given vulnerability [*scenario*](../scenario).

## Semantics

An *impact* is either *logical* or *physical*.

- A *logical impact* is a virtual effect, resulting from an action, that affects information processed by a device or the operational state of a device that processes information.

    Common examples include loss, disclosure, or corruption of information, or unexpected changes to the execution state of hardware or software.

    Logical impacts are defined using the [`hasLogicalImpact`](#logical-impact) property.

- A *physical impact* is an effect, resulting from an action, that affects something tangible, such as a physical device, machinery, the surrounding environment, or person.

    Common examples include damage to assets, people or loss of resources.

    Physical impacts are defined using the [`hasPhysicalImpact`](#physical-impact) property.

Given that an *impact* is associated with an [action](../action), the *impact* is considered to be relative to the *action's* [*context*](../action#affected-context). Thus, the impact's [*criticality*](#criticality) needs to be considered relative to the action's context. For a given context, such as `Guest OS` or `Application`, the criticality should reflect how significant an associated impact could be for the specific context.

For example, an impact in a `Guest OS` context may be of lower significance than the same impact in a `Host OS` context, which should be reflected accordingly by the impact's criticality.

## Properties

An impact MUST define either a [`hasLogicalImpact`](#logical-impact) or [`hasPhysicalImpact`](#physical-impact) property.

An *impact* has the following properties.

### Identifier

{{%usa-tag%}}Name{{%/usa-tag%}} `id`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} A globally unique identifier for the impact.

The impact identifier distinguishes the impact from other impacts related to the same vulnerability.

This identifier MUST be a version 4 (random) or 5 (SHA-1 based) Universally Unique Identifier (UUID) as defined by [RFC 4122](https://www.rfc-editor.org/rfc/inline-errata/rfc4122.html).

### Scope

{{%usa-tag%}}Name{{%/usa-tag%}} `hasScope`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} A coarse measure of the extent of impact an exploit could have on a target.

The value of `hasScope` MUST be a value from the [scope value list](../../values/scope).

Impacts with an `Unlimited` scope SHOULD assign a `hasCriticality` property value of `High`.

### Criticality

{{%usa-tag%}}Name{{%/usa-tag%}} `hasCriticality`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} A measure of the relative significance of the associated Scope.

The value of `hasCriticality` MUST be a value from the [criticality value list](../../values/criticality).

### Logical Impact

{{%usa-tag%}}Name{{%/usa-tag%}} `hasLogicalImpact`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} A virtual effect, resulting from an action, that affects information processed by a device or the operational state of a device that processes information.

Logical impact is considered for assessing traditional notions of confidentiality, integrity and availability.

The property `hasLogicalImpact` MUST NOT be used in combination with the property `hasPhysicalImpact`. These properties are mutually exclusive.

The value of `hasLogicalImpact` MUST be a value from the [logical impact value list](../../values/logical-impact).

### Location

{{%usa-tag%}}Name{{%/usa-tag%}} `hasLocation`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} zero or one
{{%usa-tag%}}Description{{%/usa-tag%}} Designating the specific area or location impacted. Serves as supplemental information for a logical impact.

The property `hasLocation` MAY be used in combination with the property `hasLogicalImpact`.

The property `hasLocation` MUST NOT be used in combination with `hasPhysicalImpact`. The property `hasLocation` only applies to logical impacts.

The value of `hasLocation` MUST be a value from the [location value list](../../values/location).

### Physical Impact

{{%usa-tag%}}Name{{%/usa-tag%}} `hasPhysicalImpact`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} A tangible impact to a physical device, machinery, the surrounding environment, or people.

The property `hasPhysicalImpact` MUST NOT be used in combination with the property `hasLogicalImpact`. These properties are mutually exclusive.

The value of `hasPhysicalImpact` MUST be a value from the [physical impact value list](../../values/physical-impact).

## Relationships

None

## Graph View

![Impact Graph](/figures/graphsnippets/ImpactSnippet.png "Impact Graph")
