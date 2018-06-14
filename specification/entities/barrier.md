# Barrier Entity

Any characteristic inherent in the vulnerability that could impede the adversary from achieving successful exploitation. A barrier increases the difficulty an attacker faces when attempting to execute an exploit for the vulnerability.

## Attributes

### The *barrier* attribute

**Cardinality**: One or many

#### Valid values

The barrier attribute value must be one of the following values or sub-values. A sub-value implies the parent value:

- **Environmental Condition**:  The exploit scenario requires an environmental condition external to the vulnerable software that is not necessarily related to the vulnerable software itself. A congested network would be an example of an environmental condition.
- **Precondition Required**:  Information about the target is necessary in order to exploit the vulnerability on a specific target. For example, the hostname of the device may be necessary in order to exploit the vulnerability on that device.
- **Privilege Required**:  The exploit scenario requires an attacker to have certain privileges prior to successful exploitation attempts.
    - **Multiple Authentication**: Exploiting the vulnerability requires that the attacker authenticate two or more times, even if the same credentials are used each time. An example is an attacker authenticating to an operating system in addition to providing credentials to access an application hosted on that system.
  - **Privilege Level**:Abstraction to assist in capturing relative privilege levels. The abstraction is only for the sake of discussing the vulnerability and is not intended to communicate the actual granular privileges that exist in most information system environments. See [Privilege Level](privilege-level.md)
- **Race Condition**:  The exploit scenario includes requiring an attacker to take advantage of a race condition.
  - **No Control**:  An attacker has no control over how the race condition will be triggered. The attacker must be fortunate to encounter the race condition.
  - **Partial Control**:  An attacker is able to start one or more of the inputs which take part in the race condition but does not have control over all inputs. For example a vulnerability exists in the processing of a particular type of input on the intial start-up of a device and an attacker must supply that input during the period when the device is starting up and the attacker has no control over when the device starts up
  - **Full Control**:  An attacker is able to routinely start all inputs which will trigger the race condition.
- **Social Engineering**:  The exploit scenario requires that an attacker perform some type of social engineering to achieve a successful exploit attempt. Typically, an attacker convinces a victim to interact with a malicious resource.
    - **Engineering Method**: The method or mechanism used to manipulate a user into interacting with a malicious resource. See [Engineering Method](engineering-method.md).
	- **Victim Type**: When a user is targeted through the use of Social Engineering the Victim Type is used to describe the possible Privilege Level values along with the Context of those privileges. The level of privilege the target has should be reflected in the Logical Impact and Physical Impact values selected. See [Victim Type](victim-type.md).
- **Specialized Condition**:  The exploit scenario requires specific, non-default configuration settings within the vulnerable software. For example, the use of a non-standard port for a networked service like ssh.

Data elements:
- value: (required) A unique namespace-qualified identifier for the barrier.

Example:
```
value: Environmental Condition
```
