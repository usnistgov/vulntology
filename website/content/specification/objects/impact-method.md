---
title: "Impact Method"
---

# Impact Method Object

A description of the method used to exploit a [*vulnerability*](../vulnerability) providing some additional information on the impact of exploitation. These are intended to be high level concepts that lead to more granular impacts as referenced in the logical and physical impact entities.

## Properties

An *impact method* has the following properties.

### Type

{{%usa-tag%}}Name{{%/usa-tag%}} `hasImpactMethodType`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} The approach used to achieve an impact.

Based on the *impact method's* type, some properties will be required when noted in the property.

The value of `hasImpactMethodType` MUST be a value from the [impact method type value list](../../values/impact-method-type).

### Gained Privilege

{{%usa-tag%}}Name{{%/usa-tag%}} `hasGainedPrivilege`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} zero or one
{{%usa-tag%}}Description{{%/usa-tag%}} Abstraction to assist in capturing relative privilege levels. The abstraction is only for the sake of discussing the vulnerability and is not intended to communicate the actual granular privileges that exist in most information system environments.

Each `hasGainedPrivilege` relates to one privilege level. Multiple *impact methods* need to be defined to describe multiple privileges gained.

The property `hasGainedPrivilege` MUST only be used when the property `hasImpactMethodType` has the value `Privilege Escalation`.

If provided, the value of `hasGainedPrivilege` MUST be a value from the [privilege level value list](../../values/privilege-level).

### Escape Context

{{%usa-tag%}}Name{{%/usa-tag%}} `hasEscapeContext`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} The association denotes where a sandbox breakout originated.

Each `hasEscapeContext` relates to one context. Multiple *impact methods* need to be defined to describe multiple context relations.

The property `hasEscapeContext` MUST only be used when the property `hasImpactMethodType` has the value `Context Escape`.

If provided, the value of `hasEscapeContext` MUST be a value from the [context value list](../../values/context).

## Relationships

None

## Graph View

![Impact Method Graph](/figures/graphsnippets/ImpactMethodSnippet.png "Impact Method Graph")
