---
title: "Entity Role"
---
# Entity Role Values

Describes the role an associated Context performs in the vulnerability scenario being described.

## Values

- **Security Authority**:  See [CVSS v3.1 Section 2.2](https://www.first.org/cvss/v3.1/specification-document#2-2-Scope-S) for a full description of security authorities.
  - **Primary**:  Associated Context is the primary security authority of the vulnerability scenario. 
  - **Secondary**:  Associated Context is a secondary security Authority of the vulnerability scenario. 
- **Component**:  See [CVSS v3.0 Section 2.2](https://www.first.org/cvss/v3.0/specification-document#2-2-Scope-S) for a full description of security authorities.
  - **Vulnerable**: Associated Context is considered to contain the vulnerability.
  - **Impacted**:  Associated Context is is where impacts of the vulnerability are realized. The Impacted Component may or may not be the Vulnerable Component.

## Graph View

![Entity Role Graph](/figures/graphsnippets/EntityRoleSnippet.png "Entity Role Graph")
