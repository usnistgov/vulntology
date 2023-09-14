---
title: "Action"
---

# Action Object

An *action* is an activity resulting in an impact to an [*affected context*](#context), that occurs within a given [*scenario](../scenario).

## Semantics

An *action* involves one or more high-level [*impact methods*](../impact-method) which occur in a specific [*affected context*](#affected-context). Actions can result in impacts to the *affected context*. If multiple contexts are affected there will be multiple *actions*, with each *action* relating to a specific *affected context*.

## Properties

An *action* has the following properties.

### Identifier

{{%usa-tag%}}Name{{%/usa-tag%}} `id`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} A globally unique identifier for the action.

The action identifier distinguishes the *action* from other actions related to the same *vulnerability*.

This identifier MUST be a version 4 (random) or 5 (SHA-1 based) Universally Unique Identifier (UUID) as defined by [RFC 4122](https://www.rfc-editor.org/rfc/inline-errata/rfc4122.html).

### Name

{{%usa-tag%}}Name{{%/usa-tag%}} `hasName`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} zero or one
{{%usa-tag%}}Description{{%/usa-tag%}} A name or label to assist in identifying a given action in the context of the containing Vulnerability.

A given action name MUST be unique across all sibling actions.

### Affected Context

{{%usa-tag%}}Name{{%/usa-tag%}} `affectsContext`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} The conceptual entity where the impacts are realized from successful completion of an action.

By associating actions with an affected context for a given scenario, different impacts can be defined for the same context across different scenarios.

The value of `affectsContext` MUST be a value from the [context value list](../../values/context).

### Context Entity Role

{{%usa-tag%}}Name{{%/usa-tag%}} `hasEntityRole`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} Describes the role an associated [*affected context*](#affected-context) performs in the *action*.

The value of `hasEntityRole` MUST be a value from the [entity value list](../../values/entity-role).

## Relationships

An *action* has the following relationships.

### Impact Method

{{%usa-tag%}}Name{{%/usa-tag%}} `hasImpactMethod`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one or many
{{%usa-tag%}}Description{{%/usa-tag%}} Provides additional information about the approach used to carry out the *action*.

The object value of the `hasImpactMethod` relationship MUST be an [impact method](../impact-method) object.

### Impact Result

{{%usa-tag%}}Name{{%/usa-tag%}} `resultsInImpact`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one or many
{{%usa-tag%}}Description{{%/usa-tag%}} An [*impact*](../impact) that will occur due to an Action.

The object value of the `resultsInImpact` relationship MUST be an [impact](../impact) object.

### Impact Non-Result

{{%usa-tag%}}Name{{%/usa-tag%}} `doesNotResultInImpact`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} zero or many
{{%usa-tag%}}Description{{%/usa-tag%}} An [*impact*](../impact) that will not occur due to an Action.

Can be used to indicate that a specific impact is not accomplished by the *action*.

The object value of the `doesNotResultInImpact` relationship MUST be an [impact](../impact) object.

## Graph View

![Action Graph](/figures/graphsnippets/ActionSnippet.png "Action Graph")