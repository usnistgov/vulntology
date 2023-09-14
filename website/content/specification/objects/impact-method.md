---
title: "Impact Method"
---

# Impact Method Object

A description of the method used to exploit a vulnerability providing some additional information on the impact of exploitation. These are intended to be high level concepts that lead to more granular impacts as referenced in the logical and physical impact entities.

## Properties

An *impact method* has the following properties.

### Type

{{%usa-tag%}}Name{{%/usa-tag%}} `hasImpactMethodType`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} The nature of impact.  See [Impact Method Types](../../values/impact-method-type).

### Gained Privilege

{{%usa-tag%}}Name{{%/usa-tag%}} `hasGainedPrivilege`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one - see notes
{{%usa-tag%}}Description{{%/usa-tag%}} Abstraction to assist in capturing relative privilege levels. The abstraction is only for the sake of discussing the vulnerability and is not intended to communicate the actual granular privileges that exist in most information system environments. See [Privilege Level](../../values/privilege-level)

   Notes:
   - *Applies only when the **hasImpactMethodType**=`Privilege Escalation`*
   - *Each `hasGainedPrivilege` relates to one privilege level*.

### Escape Context

{{%usa-tag%}}Name{{%/usa-tag%}} `hasEscapeContext`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one - see notes
{{%usa-tag%}}Description{{%/usa-tag%}} The association denotes where a sandbox breakout originated. See [Context Types](../../values/context).

   Notes:
   - *Applies only when the **hasImpactMethodType**=`Context Escape`*
   - *Each Context Escape relates to one context.*

## Relationships

None

## Graph View

![Impact Method Graph](/figures/graphsnippets/ImpactMethodSnippet.png "Impact Method Graph")