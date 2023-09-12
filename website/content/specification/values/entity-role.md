---
title: "Entity Role"
---
# Entity Role Values

Describes the role an associated Context performs in the vulnerability scenario being described.

## Values

- **Security Authority**:
	- **Primary**:  Associated Context is the primary security authority of the vulnerability scenario. See [CVSS v3.1 Section 2.2](https://www.first.org/cvss/specification-document#2-2-Scope-S) for a full description of security authorities.
	- **Secondary**:  Associated Context is a secondary security Authority of the vulnerability scenario. See [CVSS v3.1 Section 2.2](https://www.first.org/cvss/specification-document#2-2-Scope-S) for a full description of security authorities.
- **Component**:
	- **Vulnerable**: Associated Context is considered to contain the vulnerability. 
	- **Impacted**:  Associated Context is is where impacts of the vulnerability are realized. The Impacted Component may or may not be the Vulnerable Component.

## Graph View

![Entity Role Graph](/figures/graphsnippets/EntityRoleSnippet.png "Entity Role Graph")
