# Victim Type Entity

When a user is targeted through the use of Social Engineering the Victim Type is used to describe the possible Privilege Level values along with the Context of those privileges. The level of privilege the target has should be reflected in the Logical Impact and Physical Impact values selected.

## Attributes

### The *victim type* attribute

**Cardinality**: Many

Valid Values:


 - **Context**:  The entity from where the victim's authorization scope resides. See [Context](context.md).
 - **Privilege Level**:  Abstraction to assist in capturing relative privilege levels. The abstraction is only for the sake of discussing the vulnerability and is not intended to communicate the actual granular privileges that exist in most information system environments. See [Privilege Level](privilege-level.md)
 
  
Data elements:
- value: (required) A unique namespace-qualified identifier for each privilege level.

Example:
```
Value: HostOS
Value: Administrator
```
