# Impact Method Entity

A description of the method used to exploit a vulnerability providing some additional information on the impact of exploitation.

## Attributes

### The *impact method* attribute

**Cardinality**: One or many

#### Valid values

The impact method attribute value must be one of the following values or sub-values. A sub-value implies the parent value:

- **Authentication Bypass**:  Exploitation of the Vulnerability takes advantage of a failure to identify the adversary properly, directly leading to additional access or permissions.
- **Code Execution**:  Exploitation of the Vulnerability allows an adversary to execute unauthorized code, causing an impact to a Context.
- **Context Escape**:  The Vulnerability allows an adversary to exploit a trust mechanism by breaking out of a sandbox and into another workspace. This Impact Method noun group value is intended to be associated with the Context that has been escaped.
  - **Context**: One and only one Context value shall be associated with Context Escape. (The association denotes where a sandbox breakout originated.) See [Context](context.md).
- **Trust Failure**:  Exploitation of the Vulnerability takes advantage of an assumed trust relationship leading to unexpected impacts. Examples include failures of inherent trust, failure to verify a communicator, or the content being transmitted.
  - **Failure to establish trust**:  The Context failed to verify the input originated from a trusted source, in other words a check is missing or non-existent.
  - **Failure to verify content**:  The Context failed to ensure the content supplied is the expected content, is properly formatted and/or sanitized.
  - **Failure to verify receiver**:  The Context failed to ensure the entity on the receiving end of the communication is the intended entity.
  - **Failure to verify transmitter**:  The Context failed to ensure the entity on the transmitting end of the communication is the intended entity.
- **Man-in-the-Middle**:  The exploit scenario requires that an adversary perform a Man-in-the-Middle (MitM) attack. MitM attacks involve an adversary positioning themselves inside a communication channel between two or more parties. This is usually accomplished by exploiting a trust mechanism and tricking both ends of the communication channel into believing that they are communicating with the intended party. Once successfully injected into a communication channel, the MitM is capable of sensitive data disclosure, modification of data being transmitted, transmission of false data to either party (impersonation) or denial of communication to either party.

Data elements:
- value: (required) A unique namespace-qualified identifier for the barrier.

Example:
```
value: Code Execution
```

## Relationships

* Logical Impact:  One or many Logical Impacts shall be associated with Impact Method

* Physical Impact:  Zero or many Physical Impacts should be associated with Impact Method