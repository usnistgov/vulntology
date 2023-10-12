---
title: "Privilege Level"
---

# Privilege Level Values

Abstraction to assist in capturing relative privilege levels. The abstraction is only for the sake of discussing the vulnerability and is not intended to communicate the actual granular privileges that exist in most information system environments. Privilege Level MUST be considered in concert with the Context to which it is relevant. That is, for a given Context (such as `Guest OS` or `Application`), the Privilege Level should reflect a reasonably appropriate mapping based on the security posture of the specific Context.

## Values

- **Anonymous**:  No privileges required.
- **Generic Trust**:  This level is for applications or software packages that allow public account creation. Meaning that anyone who has access to the software has the ability to create an account and access basic functionality.
- **User**:  Representative of a generic or basic user.
- **Privileged**:  Representative of something more than a basic user, but not the full control of an Administrator
- **Administrator**:  Representative of when the privilege allows complete or nearly complete access to the context. Common terms include Admin, Administrator, Root, System or Kernel.

## Graph View

![Privilege Level Graph](/figures/graphsnippets/PrivilegeLevelSnippet1.png "Privilege Level Graph")

---
![Privilege Level Graph](/figures/graphsnippets/PrivilegeLevelSnippet2.png "Privilege Level Graph")
