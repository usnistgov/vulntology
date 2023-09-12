---
title: "Barrier Types"
---

# Barrier Types

There are multiple types of Barriers and each type has one or more subtypes which represent concepts more nuanced than their parent types.
	
- **Authentication/Authorization**:
	- **Impersonation**:
		- **Encryption**: Data or access to communication is protected through a mechanism that converts information into code or cipher.
		- **On Path**:  The exploit scenario requires that an adversary is able to position themselves inside a communication channel between two or more parties. This is usually accomplished by exploiting a trust mechanism and tricking both ends of the communication channel into believing that they are communicating with the intended party. Once successfully injected into a communication channel, the adversary is capable of sensitive data disclosure, modification of data being transmitted, transmission of false data to either party (impersonation) or denial of communication to either party.
        - **Privilege Required**: Privilege is to overcome the barrier.
		- **Social Engineering**: The exploit scenario requires that an attacker perform some type of social engineering to achieve a successful exploit attempt. Typically, an attacker convinces a victim to interact with a malicious resource.

 - **Obfuscation**: The attacker must overcome a protection mechanism in place that deliberately creates confusing or difficult to determine values or locations for resources or data.
	- **ASLR**: Some form of address space layout randomization (ASLR) is in use that must be defeated to recognize impacts
	- **Dynamic Compilation**: The relationship of the source code and the executable is non-predictable
 - **State**:  Unique conditions exist either in process timing, implementation, architectural environment or particular configurations of a given system or systems within its influence. 
    - **Race Condition**:  The exploit scenario includes requiring an attacker to take advantage of a race condition.
    
        Race Condition has multiple subtypes that can be assigned. These values provide additional detail on the level of likely control an adversary has to trigger the vulnerable race condition. Note that this is only a description of how much control an attacker has over the inputs involved in the race condition and not an indication of the reproducibility of triggering the race condition itself.

        - **No Control**:  An attacker has no control over how the race condition will be triggered. The attacker must be fortunate to encounter the race condition.
        - **Partial Control**: An attacker is able to start one or more of the inputs which take part in the race condition but does not have control over all inputs. For example a vulnerability exists in the processing of a particular type of input on the initial start-up of a device and an attacker must supply that input during the period when the device is starting up and the attacker has no control over when the device starts up.
        - **Full Control**:  An attacker is able to routinely start all inputs which will trigger the race condition.

    - **Specialized Condition**:  The exploit scenario requires specific, non-default configuration settings within the vulnerable software. For example, the use of a non-standard port for a networked service like ssh.
    - **Environmental Condition**:  The exploit scenario requires an environmental condition external to the vulnerable software that is not necessarily related to the vulnerable software itself. A congested network would be an example of an environmental condition.
    - **Precondition Required**:  Information about the target is necessary in order to exploit the vulnerability on a specific target. For example, the hostname of the device may be necessary in order to exploit the vulnerability on that device.
  - **Boundary Protections**:  The attacker must be able to move through explicit boundaries that otherwise would prevent successful exploitation
    - **Sandbox**:  The product is deployed within a sandbox that must be broken out of to recognize impacts
    - **Container**:  The product is deployed within a type of container that must be broken out of to recognize impacts.

## Graph View

![Race Condition Graph](/figures/graphsnippets/RaceConditionSnippet.png "Race Condition Graph")
