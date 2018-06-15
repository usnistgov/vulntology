# Engineering Method Entity

The method or mechanism used to manipulate a user into interacting with a malicious resource.

## Attributes

### The *engineering method* attribute

**Cardinality**: One or many

Valid Values:
The engineering method attribute value must be one of the following values

 - **Malicious Application**:  An application that has been modified or crafted to perform operations that are unintended by the victim
 - **Malicious File**:  A file that has been crafted in a way that causes a target program to operate in an unintended fashion
 - **Malicious Link**:  A URL or hyperlink that has been crafted in a way that causes a target program or website to operate in an unintended fashion
 - **Malicious Website Content**:  A website that has been crafted in a way that causes a target program to operate in an unintended fashion or is used to simulate a site that the target user trusts.
 
Data elements:
- value: (required) A unique identifier for each engineering method.

Example:
```
Value: Malicious Website
```
