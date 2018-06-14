# Product Entity

The software and/or hardware configurations that are known to be vulnerable to exploitation of the Vulnerability. Different Product configurations can be associated with different Scenarios to allow for description of varying impacts and exploitation mechanisms.

## Attributes

### The *product* attribute

**Cardinality**: One or many

A list of identifiers or an applicability language which allows for the description of the product configuration. Example product identifiers are Software Identifiers (SWID) as described in [ISO/IEC 19770-2:2015] and Common Platform Enumeration (CPE) names as described in [CPEN]. An example of an applicability language would be the CPE Applicability Language described in [CPEAL].

Data elements:
- namespace: (required) The specific grouping of unique identifiers. 
- value: (required) A unique namespace-qualified identifier for each product.

Example:
```
Namespace: http://standards.iso.org/iso/19770/-2/2015 
Value: 2001-06.com.acme_ACME_Application-1.01
```
