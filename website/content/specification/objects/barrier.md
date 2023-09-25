---
title: "Barrier"
---

# Barrier Object

This could be any characteristic inherent in the vulnerability that could impede the adversary from achieving successful exploitation or a protection mechanism that may limit the actions or impact that can be taken even if the vulnerability is able to be exploited. These are often part of the system in which the product is deployed or are inherent in how the product is used.

## Properties

### Identifier

{{%usa-tag%}}Name{{%/usa-tag%}} `id`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} A globally unique identifier for the *barrier*.

The action identifier distinguishes the *barrier* from other *barriers* related to the same *vulnerability*.

This identifier MUST be a version 4 (random) or 5 (SHA-1 based) Universally Unique Identifier (UUID) as defined by [RFC 4122](https://www.rfc-editor.org/rfc/inline-errata/rfc4122.html).

### Type

{{%usa-tag%}}Name{{%/usa-tag%}} `hasBarrierType`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one
{{%usa-tag%}}Description{{%/usa-tag%}} Identifies the kind of barrier. Based on the barrier's type, [additional properties](#additional-properties) may be required. (See [Barrier Types](../../values/barrier-type))

## Additional Properties

Each subtype can require type specific properties in addition to those inherited from their parent type. For example, Social Engineering could be assigned as a barrier type and would have the "Privileges Needed", "Privilege Context" and "Engineering Method" properties.

### Needed Privilege

{{%usa-tag%}}Name{{%/usa-tag%}} `hasNeededPrivilege`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} zero or one - see notes
{{%usa-tag%}}Description{{%/usa-tag%}} The privileges that are needed relative to the type of barrier being overcome. (See [Privilege Levels](../../values/privilege-level))

Notes:

* Applies only when the **hasBarrierType**=`Authentication/Authorization::Privileges Required` or **hasBarrierType**=`Authentication/Authorization::Impersonation::Social Engineering`.
* Required when **hasBarrierType**=`Authentication/Authorization::Privileges Required`, optional otherwise.
* Each `hasNeededPrivilege` relates to one privilege level.

### Engineering Method

{{%usa-tag%}}Name{{%/usa-tag%}} `hasEngineeringMethod`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} one or many - see notes
{{%usa-tag%}}Description{{%/usa-tag%}} The method or mechanism used to manipulate a user into interacting with a malicious resource. (See [Engineering Method](../../values/engineering-method)).

Notes:

* Applies only when the **hasBarrierType**=`Authentication/Authorization::Impersonation::Social Engineering`.
* Each `hasEngineeringMethod` relates to one engineering method.

### Related Context

{{%usa-tag%}}Name{{%/usa-tag%}} `relatesToContext`
{{%usa-tag%}}Cardinality{{%/usa-tag%}} zero or one - see notes
{{%usa-tag%}}Description{{%/usa-tag%}} The context to which the privileges are related (See [Context](../../values/context))

Notes:

* Applies only when the **hasBarrierType**=`Authentication/Authorization::Impersonation::Social Engineering`, **hasBarrierType**=`Boundary Protections`, **hasBarrierType**=`Boundary Protections::Container`, or , **hasBarrierType**=`Boundary Protections::Sandbox`.
* Each `hasEngineeringMethod` relates to one context.

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
      "neededPrivileges": "User",
      "relatesToContext": "Application"
    },
    {
      "id": "S1B2",
      "hasBarrierType": "Authentication/Authorization::Privileges Required",
      "neededPrivileges": "User",
      "relatesToContext": "Application"
    }
  ]
}
```

## Graph View

 ![Barrier Graph](/figures/graphsnippets/BarrierSnippet.png "Barrier Graph")
