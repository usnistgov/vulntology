# Entity Role Entity

Describes the role an associated Context performs in the vulnerability scenario being described.

## Attributes

### The *entity role* attribute

**Cardinality**: One or many

Valid Values:

- **Vulnerable**:  Associated Context contains the Vulnerability
- **Primary Authorization**:  Associated Context is the main or initial authorization scope of the vulnerability scenario. See section 2.2 in [CVSSV3] for a full description of authorization scope.
- **Secondary Authorization**:  Associated Context is the secondary authorization scope of the vulnerability scenario. See section 2.2 in [CVSSV3] for a full description of authorization scope.

Data elements:
- value: (required) A unique identifier for the entity role.

Example:
```
value: Vulnerable
value: Primary Authorization
```
