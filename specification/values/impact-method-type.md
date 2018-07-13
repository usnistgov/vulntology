# Impact Method Type

A description of the method used to exploit a vulnerability providing some additional information on the impact of exploitation. These are intended to be high level concepts that lead to more granular impacts as referenced in the logical and physical impact entities.

## Values

Items that are indented represent more specific values that can be used to describe the parent value. For instance, choosing "Failure to Verify Content" as a value would imply "Trust Failure" as well.

- **Authentication Bypass**:  Exploitation of the Vulnerability takes advantage of a failure to identify the adversary properly, directly leading to additional access or permissions.
- **Code Execution**:  Exploitation of the Vulnerability allows an adversary to execute unauthorized code, causing an impact to a Context.
- **Context Escape**:  The Vulnerability allows an adversary to exploit a trust mechanism by breaking out of a sandbox and into another workspace. This Impact Method noun group value is intended to be associated with the Context that has been escaped.
  - **ExcapedContext**: One and only one Context value shall be associated with Context Escape. (The association denotes where a sandbox breakout originated.) See [Context Types](context-type.md). <br /> *Each Context Escape relates to one context.*
- **Trust Failure**:  Exploitation of the Vulnerability takes advantage of an assumed trust relationship leading to unexpected impacts. Examples include failures of inherent trust, failure to verify a communicator, or the content being transmitted.
  - **Failure to Establish Trust**:  The Context failed to verify the input originated from a trusted source, in other words a check is missing or non-existent.
  - **Failure to Verify Content**:  The Context failed to ensure the content supplied is the expected content, is properly formatted and/or sanitized.
  - **Failure to Verify Receiver**:  The Context failed to ensure the entity on the receiving end of the communication is the intended entity.
  - **Failure to Verify Transmitter**:  The Context failed to ensure the entity on the transmitting end of the communication is the intended entity.

  
