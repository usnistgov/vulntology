# Mitigation Entity

Describes protection mechanisms that may limit the impact or actions that can be taken even if the vulnerability is able to be exploited. These mechanisms are often part of the system in which the product is deployed or are inherent in how the product is used.

## Attributes

### The number attribute

**Cardinality**: Zero or many

Valid Values:
The mitigation attribute value must be one of the following values

- **ASLR**:  Some form of Address space layout randomization (ASLR) is in use.
- **HPKP/HSTS**:  HTTP Public Key Pinning (HPKP) or HTTP Strict Transport Security (HSTS) is in use.
- **Multi-Factor Authentication**:  Some form of Multi-Factor Authentication is required to access the product.
- **Physical Security**:  Some form of physical security is in place that would mitigate this vulnerability.
- **Sandboxed**:  The product is deployed within a sandbox.
  
Data elements:
- namespace: (required) The specific grouping of unique identifiers. 
- value: (required) A unique namespace-qualified identifier for each mitigation.

Example:
```
Namespace: https://csrc.nist.gov/publications/nistir8138/mitigation 
Value: ASLR
```
