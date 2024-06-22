---
{"dg-publish":true,"permalink":"/os-lm-19/virtualization-and-security/","dgPassFrontmatter":true}
---

### Virtualization

1. **Definition**:
    
    - Running multiple virtual instances on a single physical hardware resource.
    - Ensuring virtualized hardware infrastructure is secure and protected.
    
2. **Operating System-Based Virtualization**:

	![Pasted image 20240622211641.png](/img/user/Pasted%20image%2020240622211641.png)
    - Kernel enables isolated user-space instances.
    - Virtualization software installed over a pre-existing operating system (host OS).
3. **Major Operating System-Based Services**:
    
    - Backup and Recovery
    - Security Management
    - Integration to Directory Services
4. **Operations**:
    
    - Utilize hardware capabilities (network connection, CPU).
    - Interact with peripherals (webcam, printer, keyboard).
    - Read/write data (files, folders, network shares).
5. **Components of OS Virtualization**:
    
    - OS Virtualization Server: Manages streaming and client connections.
    - Client: Connects to server and runs OS from virtual disk.
    - Supporting components: Database, streaming service, TFTP service, PXE boot service.
6. **Process**:
	- Connect to OS Virtualization server.
    - Server checks client and assigns virtual disk.
    - Virtual disk content is streamed to the client.
8. **Features**:
    
    - Resource Isolation
    - Lightweight
    - Portability
    - Scalability
    - Security
    - Reduced Overhead
    - Easy Management
8. **Advantages**:
    
    - Resource Efficiency
    - High Scalability
    - Easy Management
    - Reduced Costs
    - Faster Deployment
    - Portability
9. **Disadvantages**:
    
    - Security risks due to shared host OS.
    - Limited Isolation
    - Complexity
    - Dependency Issues
    - Limited Hardware Access

### Security in Operating Systems

1. **Steps to Ensure Virtual Security**:
    - Isolate and segregate assets.
    - Harden and patch OS regularly.
    - Monitor and audit continuously.
    - Backup and recover data periodically.
    - Educate and train staff and users.
    - Use security tools designed for virtualized environments.
    
1. **Types of Attacks on OS**:
    - **Active Attacks**:
        - Masquerade
        - Modification of messages
        - Repudiation
        - Replay
        - Denial-of-Service (DoS)
        
    - **Passive Attacks**:
        - Monitoring communications
        
    - **Malware**:
        - Spyware, ransomware, viruses, worms
        
    - **Phishing**:
        - Forged communications to steal sensitive information
        
    - **Man-in-the-Middle Attack (MITM)**:
        - Intercepting and altering communications
        
    - **Distributed Denial-of-Service (DDoS) Attack**:
        - Flooding server with simultaneous data requests
        
    - **Zero-Day Exploit**:
        - Exploiting network vulnerabilities before patches are applied
    
1. **Prevention Measures**:
    - Regular OS updates.
    - Strong authentication methods.
    - Use of reputable security software.
    - Employ firewalls.
    - Limit privileges and access rights.
    - Continuous monitoring and penetration testing.