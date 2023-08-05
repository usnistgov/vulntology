# Barrier Object

This could be any characteristic inherent in the vulnerability that could impede the adversary from achieving successful exploitation or a protection mechanism that may limit the actions or impact that can be taken even if the vulnerability is able to be exploited. These are often part of the system in which the product is deployed or are inherent in how the product is used.

## Properties

- **id** (one): A globally unique identifier for the impact that distinguishes it from other impacts related to the same vulnerability.
- **hasBarrierType** (one): Identifies the kind of barrier. Based on the barrier's type, [additional properties](#additional-properties) may be required.

## Additional Properties

Each subtype can require type specific properties in addition to those inherited from their parent type. For example, Social Engineering could be assigned as a barrier type and would have the "Privileges Needed", "Privilege Context" and "Engineering Method" properties.

- **hasNeededPrivilege** (zero or one - see notes): The privileges that are needed relative to the type of barrier being overcome. (See [Privilege Levels](../values/privilege-level.md))

   Notes:
   - *Applies only when the **hasBarrierType**=`Authentication/Authorization::Privileges Required` or **hasBarrierType**=`Authentication/Authorization::Impersonation::Social Engineering`*
   - Required when **hasBarrierType**=`Authentication/Authorization::Privileges Required`, optional otherwise
   - *Each `hasNeededPrivilege` relates to one privilege level*.

- **hasEngineeringMethod** (one or many - see notes): The method or mechanism used to manipulate a user into interacting with a malicious resource. (See [Engineering Method](../values/engineering-method.md)). 

   Notes:
   - *Applies only when the **hasBarrierType**=`Authentication/Authorization::Impersonation::Social Engineering`*
   - *Each `hasEngineeringMethod` relates to one engineering method*.

- **relatesToContext** (zero or one - see notes): The context to which the privileges are related (See [Context](../values/context.md))

   Notes:
   - *Applies only when the **hasBarrierType**=`Authentication/Authorization::Impersonation::Social Engineering`, **hasBarrierType**=`Boundary Protections`, **hasBarrierType**=`Boundary Protections::Container`, or , **hasBarrierType**=`Boundary Protections::Sandbox`
   - *Each `hasEngineeringMethod` relates to one context*.

## Example Use

```json
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
```

## Graph View
 ![Barrier Graph](../figures/graphsnippets/BarrierSnippet.png "Barrier Graph")
