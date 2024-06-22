---
{"dg-publish":true,"permalink":"/os-lm-18/hyper-visors-and-virtual-machines/","dgPassFrontmatter":true}
---

#### 1. Virtual Machine Monitor / Manager (Hypervisor)

- **Definition**: A layer of software/firmware managing multiple VMs on a single physical host.
    
- **Types of Hypervisors**:
    
    - **Type 1 (Bare Metal)**: Runs directly on hardware. Examples: VMware ESXi, Microsoft Hyper-V Server, Xen.
    - **Type 2 (Hosted)**: Runs on an existing OS. Examples: VMware Workstation, Oracle VirtualBox, Parallels Desktop.
- **Key Functions**:
    
    - Virtualization
    - Resource Allocation
    - Isolation
    - Hardware Abstraction
- **Advantages**:
    
    - Server Consolidation
    - Isolation
    - Ease of Management
- **Use Cases**:
    
    - Data Centres
    - Development and Testing
    - Desktop Virtualization
- **Challenges**:
    
    - Performance Overhead
    - Security Concerns
    - Compatibility
- **Key Providers**: VMware, Microsoft, Citrix, Oracle
    

#### 2. Implementation Types

- **Type 1 Hypervisor**:
    
    - Direct control over hardware.
    - Efficient performance.
    - Used in enterprise environments.
- **Type 2 Hypervisor**:
    
    - Runs on top of a host OS.
    - Easier setup.
    - Used for desktops/laptops.

#### 3. Para-Virtualization

- **Implementation**: Modifies the guest OS for efficient communication with the host.
- **Example**: Xen (uses Xen-aware Linux kernel).
- **Characteristics**: Improved performance but requires guest OS modifications.

#### 4. Programming Environment Virtualization

- **Approaches**:
    
    - **Virtual Machines**: Full-fledged emulation of a computer system. Examples: VMware, VirtualBox, Hyper-V.
    - **Cloud-based Environments**: IDEs or services in the cloud. Examples: AWS Cloud9, GitHub Codespaces.
- **Advantages**: Isolation, compatibility, accessibility, collaboration.
    

#### 5. Emulation

- **Definition**: One system behaves like another.
- **Examples**: Dolphin, Parallels, Wine, Bluestacks, Xcode.
- **Advantages**: Cross-platform compatibility, low cost, space efficiency.
- **Disadvantages**: Slower performance, security risks.

#### 6. Microkernels and Exokernels

- **Microkernels**:
    
    - **Principle**: Minimize kernel functionality, delegate services to user-space.
    - **Structure**: Core services in the microkernel, additional services in user-space.
    - **Advantages**: Modularity, reliability.
    - **Disadvantages**: Performance overhead, complexity.
    - **Examples**: Mach, L4.
- **Exokernels**:
    
    - **Principle**: Expose hardware resources directly to applications.
    - **Structure**: Minimal abstractions, direct hardware management by applications.
    - **Advantages**: Performance, flexibility.
    - **Disadvantages**: Security concerns, complexity for developers.
    - **Examples**: Exokernel, Nemesis.
- **Comparison**:
    
    - **Abstraction Level**: Microkernels (higher-level), Exokernels (lower-level).
    - **Performance**: Microkernels (potential overhead), Exokernels (maximum performance).
    - **Flexibility**: Microkernels (modularity), Exokernels (direct control).
    - **Security**: Microkernels (isolation), Exokernels (application-level responsibility).

### Summary

Microkernels focus on modularity and reliability, with a small core kernel, while exokernels prioritize performance and flexibility by allowing applications direct hardware control. The choice depends on design goals and trade-offs. Hypervisors, essential for virtualization, come in two types: Type 1 for direct hardware access and Type 2 for ease of use on existing OS. Emulation and programming environment virtualization facilitate cross-platform compatibility and consistent development setups.