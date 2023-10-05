---
title: "Barrier"
---

# Barrier Object

A *barrier* can be any characteristic inherent in the [*vulnerability*](../vulnerability) that could impede the adversary from achieving successful exploitation or a protection mechanism that may limit the actions or impact that can be taken even if the vulnerability is able to be exploited. These are often part of the system in which the product is deployed or are inherent in how the product is used.

## Properties

A *barrier* defines the following properties.

Each *barrier* subtype can require type specific properties. For example, `Authentication/Authorization::Impersonation::Social Engineering` could be assigned as a barrier type and would have the `hasNeededPrivilege`, `relatesToContext` and `hasEngineeringMethod` properties.

### Identifier

{{%usa-tag%}}Name{{%/usa-tag%}} `id`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} A globally unique identifier for the *barrier*.

The action identifier distinguishes the *barrier* from other *barriers* related to the same *vulnerability*.

This identifier MUST be a version 4 (random) or 5 (SHA-1 based) Universally Unique Identifier (UUID) as defined by [RFC 4122](https://www.rfc-editor.org/rfc/inline-errata/rfc4122.html).

### Type

{{%usa-tag%}}Name{{%/usa-tag%}} `hasBarrierType`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} Identifies the kind of barrier.

Based on the *barrier's* type, some properties will be required when noted in the property.

The value of `hasBarrierType` MUST be a value from the [barrier type value list](../../values/barrier-type).

### Needed Privilege

{{%usa-tag%}}Name{{%/usa-tag%}} `hasNeededPrivilege`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} zero or one
{{%usa-tag%}}Description{{%/usa-tag%}} The privileges that are needed relative to the type of barrier being overcome.

Each `hasNeededPrivilege` relates to one privilege level. Multiple *barriers* need to be defined to describe multiple needed privileges.

The property `hasNeededPrivilege` MAY be used when the property `hasBarrierType` has the value `Authentication/Authorization::Impersonation::Social Engineering`. Use in this scenario is optional.

The property `hasNeededPrivilege` MUST be used when the property `hasBarrierType` has the value `Authentication/Authorization::Privileges Required`.

The property `hasNeededPrivilege` MUST be omitted if the property `hasBarrierType` value is not `Authentication/Authorization::Impersonation::Social Engineering` or `Authentication/Authorization::Privileges Required`.

If provided, the value of `hasNeededPrivilege` MUST be a value from the [privilege level value list](../../values/privilege-level).

### Engineering Method

{{%usa-tag%}}Name{{%/usa-tag%}} `hasEngineeringMethod`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} zero or many
{{%usa-tag%}}Description{{%/usa-tag%}} The method or mechanism used to manipulate a user into interacting with a malicious resource.

This property can be multi-valued.

The property `hasEngineeringMethod` MUST only be used when the property `hasBarrierType` has the value `Authentication/Authorization::Impersonation::Social Engineering`.

If provided, the value of `hasEngineeringMethod` MUST be a value from the [engineering method value list](../../values/engineering-method).

### Related Context

{{%usa-tag%}}Name{{%/usa-tag%}} `relatesToContext`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} zero or one
{{%usa-tag%}}Description{{%/usa-tag%}} The context to which the privileges are related.

Each `relatesToContext` relates to one context. Multiple *barriers* need to be defined to describe multiple context relations.

The property `relatesToContext` MUST only be used when the property `hasBarrierType` has the values:

- `Authentication/Authorization::Privileges Required`,
- `Authentication/Authorization::Impersonation::Social Engineering`,
- `Boundary Protections`,
- `Boundary Protections::Container`, or
- `Boundary Protections::Sandbox`.

If provided, the value of `relatesToContext` MUST be a value from the [context value list](../../values/context).

## Relationships

None

## Example

```json
{
  "blockedByBarrier": [
    {
      "id": "S1B1",
      "hasBarrierType": "Authentication/Authorization::Impersonation::Social Engineering",
      "hasEngineeringMethod": ["MaliciousLink"],
      "hasNeededPrivilege": "User",
      "relatesToContext": "Application"
    },
    {
      "id": "S1B2",
      "hasBarrierType": "Authentication/Authorization::Privileges Required",
      "hasNeededPrivilege": "User",
      "relatesToContext": "Application"
    }
  ]
}
```

## Graph View

 ![Barrier Graph](/figures/graphsnippets/BarrierSnippet.png "Barrier Graph")
