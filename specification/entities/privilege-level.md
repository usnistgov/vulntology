# Privilege Level Entity

Abstraction to assist in capturing relative privilege levels. The abstraction is only for the sake of discussing the vulnerability and is not intended to communicate the actual granular privileges that exist in most information system environments.

## Attributes

### The *privilege level* attribute

**Cardinality**: One

Valid Values:
The privilege level attribute value must be one of the following values

 - **Anonymous**:  No privileges required.
 - **Generic Trust**:  This level is for applications or software packages that allow public account creation. Meaning that anyone who has access to the software has the ability to create an account and access basic functionality.
 - **User**:  Representative of a generic or basic user.
 - **Privileged**:  Representative of something more than a basic user, but not the full control of an Administrator
 - **Administrator**:  Representative of when the privilege allows complete or nearly complete access to the context. Common terms include Admin, Administrator, Root, System or Kernel.
  
Data elements:
- namespace: (required) The specific grouping of unique identifiers. 
- value: (required) A unique namespace-qualified identifier for each privilege level.

Example:
```
Namespace: https://csrc.nist.gov/publications/nistir8138/mitigation 
Value: Administrator
```
