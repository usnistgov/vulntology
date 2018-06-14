# Known Chain Entity

An identifier for another known Vulnerability that can be used in conjunction with the Vulnerability in question to achieve a different and likely greater impact.

## Attributes

### The *vulnerability-identifier* attribute

**Cardinality**: Zero or many

An identifier for a vulnerability supplied by a source.

Examples include a knowledge base article number, patch number, a bug tracking database identifier or a common identifier such as a Common Vulnerabilities and Exposures (CVE) identifier. CVE is a widely adopted identifier used across many organizations.

Data elements:
- namespace: (required) The specific grouping of unique identifiers. 
- value: (required) A unique namespace-qualified identifier for the Vulnerability.

Example:
```
namespace: cve.mitre.org
value: CVE-2015-1234
```
