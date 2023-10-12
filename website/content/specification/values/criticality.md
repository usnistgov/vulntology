---
title: "Criticality"
---
# Criticality Values

A measure of the relative importance of the associated Scope. This is most relevant when Scope has a value of `Limited`. When Scope is `Limited`, Criticality MUST be used in order to provide additional information about its importance. Alternatively, if Scope is `Unlimited`, Criticality SHOULD be considered as `High`. Criticality MUST be considered in concert with the Context to which it is associated. That is, for a given Context (such as `Guest OS` or `Application`), the Criticality should reflect how significant an associated impact could be for the specific Context. An impact in a `Guest OS` Context may be of lower significance than the same impact in a `Host OS` Context and should be reflected accordingly by its associated Criticality.

## Values

- **Low**:  The impact is reasonably insignificant.
- **High**:  The impact is reasonably significant.

## Graph View

![Criticality Graph](/figures/graphsnippets/CriticalitySnippet.png "Criticality Graph")
