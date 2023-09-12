---
title: "Scope"
---

# Scope Values

A coarse measure of the level of impact an exploit could have on a target. In some cases, an impact has no constraints at all. An example of this is a vulnerability with a 'Read (Direct)' Logical Impact association in which the adversary has access to the entire system, and thus has no constraints. In other cases, an Impact might have some constraints in place. An example of this is `Write (Direct)` Impact where the attacker is able to modify resources only accessible by the user.

## Values

- **Limited**:  There are restrictions to the associated [impact](../../impact).
- **Unlimited**:  There are no restrictions to the associated impact.

## Graph View

![Scope Graph](/figures/graphsnippets/ScopeSnippet.png "Scope Graph")