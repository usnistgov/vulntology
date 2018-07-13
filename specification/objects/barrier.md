# Barrier Object

This could be any characteristic inherent in the vulnerability that could impede the adversary from achieving successful exploitation or a protection mechanism that may limit the actions or impact that can be taken even if the vulnerability is able to be exploited. These are often part of the system in which the product is deployed or are inherent in how the product is used.

## Types of Barrier
Types that are listed indented that do not have references to a specific set of values are considered sub-types of the parent. For example, Social Engineering could be assigned as the barrier type and would have the same properties as its parent in addition to any properties specific to Social Engineering. 
	
  - **Authentication/Authorization**:<br />
     *Type Specific Properties* <br />
     **Privileges Needed**: The privileges that are needed relative to the type of barrier being overcome. (See [Privilege Levels](../values/privilege-level-type.md)) <br /> *Each Authentication/Authorization Barrier has one Privilege Level*
    - **Impersonation**:
	  - **SocialEngineering**: The exploit scenario requires that an attacker perform some type of social engineering to achieve a successful exploit attempt. Typically, an attacker convinces a victim to interact with a malicious resource.<br />
	  *Type Specific Properties* <br />
	  **Privilege Context**: The context to which the privileges are related (See [Context Types](../values/context-type.md)).<br /> *Each Social Engineering relates to one context.* <br />
	  **Engineering Method**: The method or mechanism used to manipulate a user into interacting with a malicious resource. (See [Engineering Method](../values/engineering-method-type.md)). <br /> *Each Social Engineering has one or more Engineering Methods.*
	  - **Man-in-the-Middle**:  The exploit scenario requires that an adversary perform a Man-in-the-Middle (MitM) attack. MitM attacks involve an adversary positioning themselves inside a communication channel between two or more parties. This is usually accomplished by exploiting a trust mechanism and tricking both ends of the communication channel into believing that they are communicating with the intended party. Once successfully injected into a communication channel, the MitM is capable of sensitive data disclosure, modification of data being transmitted, transmission of false data to either party (impersonation) or denial of communication to either party.
	- **Privileges Required**: <br />
	*Type Specific Properties* <br />
	**Privilege Context**: The context to which the privileges are related (See [Context Types](../values/context-type.md)). <br /> *Each Privileges Required relates to one context.* <br />
	- **Encryption**: DESCRIPTION NEEDED
  - **Obfuscation**: DESCRIPTION NEEDED
    - **ASLR**: Some form of Address space layout randomization (ASLR) is in use that must be defeated to recognize impacts
    - **Dynamic Compilation**:  DESCRIPTION NEEDED
  - **State**:  DESCRIPTION NEEDED
    - **Race Condition**:  The exploit scenario includes requiring an attacker to take advantage of a race condition. Race Condition has multiple [Race Condition Types](../values/race-condition-type.md) that can be assigned. 
    - **Specialized Condition**:  The exploit scenario requires specific, non-default configuration settings within the vulnerable software. For example, the use of a non-standard port for a networked service like ssh.
    - **Environmental Conditon**:  The exploit scenario requires an environmental condition external to the vulnerable software that is not necessarily related to the vulnerable software itself. A congested network would be an example of an environmental condition.
    - **Precondition Required**:  Information about the target is necessary in order to exploit the vulnerability on a specific target. For example, the hostname of the device may be necessary in order to exploit the vulnerability on that device.
  - **Boundary Protections**:  DESCRIPTION NEEDED<br />
  *Type Specific Properties* <br />
  **Privilege Context**: The context to which the boudary is related(See [Context Types](../values/context-type.md)). <br /> *Each Boundary Protection relates to  one Context.*
    - **Sandbox**:  The product is deployed within a sandbox that must be broken out from to recognize impacts
    - **Container**:  The product is deployed within a type of container that must be broken out from to recognize impacts
    - **Virtualization?**:  


  
