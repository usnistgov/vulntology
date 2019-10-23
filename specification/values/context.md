# Context Values

The conceptual entity where the impacts are realized from successful exploitation of a security vulnerability. Different impacts can be realized by multiple contexts from multiple scenarios.

## Values

- **Application**:  A program designed and implemented to accomplish a specific task. Applications can run on or within operating systems, firmware or other applications.
- **Channel**:  The logical communication medium that is being used between other contexts. Channel is intended to be used when a protocol or cipher suite has a flaw inherently as opposed to an implementation issue. Examples would be failures of sufficient entropy in the cipher text or cryptographic key strength.
- **Firmware**:  Stored software that is considered to be built-in to a device. This is most commonly seen within embedded devices, routers, firewalls, BIOS and UEFI.
- **Guest OS**:  An operating system running as the foundation layer for other software applications. This is intended to be used when the Hypervisor context is applicable, otherwise Host OS should be used.
- **Host OS**:  An operating system running as the foundation layer for other software applications. This is intended to be used when the Hypervisor context is not applicable, otherwise Guest OS should be used.
- **Hypervisor**:  A program or operating system that coordinates the sharing of hardware resources for multiple operating systems. Each guest operating system appears to have its own processor, memory, and other resources to itself. However, the hypervisor is controlling the shared hardware resources, allocating what is needed to each operating system as necessary, and isolating the guest operating systems from each other.
- **Physical Hardware**:  The actual physical hardware such as the logic gates within processors, the sectors of a disk or cells within memory.

![Context Graph](../figures/graphsnippets/ContextSnippet.png "Context Graph")