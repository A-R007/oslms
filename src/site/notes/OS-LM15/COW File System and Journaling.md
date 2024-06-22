---
{"dg-publish":true,"permalink":"/os-lm-15/cow-file-system-and-journaling/","dgPassFrontmatter":true}
---

#### 1. Copy-on-Write (CoW) File Systems

- **Definition**: CoW is a resource management technique allowing parent and child processes to share the same memory pages initially. Only when a modification occurs, a copy of the page is made.
- **Usage**: Efficiently copies data resources. If the copied data is unmodified, it remains as a reference to the original.
- **Implementation**: Commonly used in the `fork()` system call, creating a child process that shares the parent's memory pages.
- **Operating Systems**: Utilized by Linux, Solaris, Windows XP.
- **Advantages**: Only modified pages are copied, reducing overhead. Free pages are allocated from a pool of zeroed-out pages.

#### 2. CoW Technique Details

- **Process Creation**: Parent and child processes share memory pages marked as copy-on-write. Modifications trigger the creation of a new page copy.
- ![Pasted image 20240622221806.png](/img/user/Pasted%20image%2020240622221806.png)
- **Example**: Process A and Process B share the same memory pages. If Process A modifies a page, a copy of that page is created for Process A.
- ![Pasted image 20240622221827.png](/img/user/Pasted%20image%2020240622221827.png)

#### 3. Journaling File Systems

- **Purpose**: Addresses file system inconsistency by logging actions before committing them to the disk.
- **Examples**: Linux ext3/ext4, Windows NTFS.
- ![Pasted image 20240622221914.png](/img/user/Pasted%20image%2020240622221914.png)
- **Components of a Journal**:
    - **TxB (Transaction Begin Block)**: Contains transaction ID (TID).
    - **Metadata Blocks**: Copies of blocks to be updated.
    - **TxE (Transaction End Block)**: Marks the end of a transaction.
- **Process**:
- ![Pasted image 20240622222159.png](/img/user/Pasted%20image%2020240622222159.png)
    1. Write actions to the journal.
    2. Commit the transaction by writing TxE.
    3. Write data to the disk (checkpoint).

#### 4. Benefits of Journaling

- **Improved Recovery Time**: Quick recovery after crashes by referring to the journal.
- **Enhanced Data Integrity**: Ensures updates are complete and recoverable.
- **Reduced Disk Scans**: Minimizes the need for full disk scans to fix inconsistencies.

#### 5. Types of Journaling File Systems

- **Physical Journaling**: Records an advance copy of every block to be written, offering high fault protection but with a performance penalty.
- **Logical Journaling**: Stores changes to metadata, offering better performance but less fault tolerance.

#### 6. Alternatives to Journaling

- **Log-Structured File Systems**: Occupy the entire storage device, avoiding the write-twice penalty.
- **Copy-on-Write File Systems**: Full CoW systems like ZFS and Btrfs avoid in-place changes by writing new data blocks and updating metadata.
- **Soft Updates**: Used in some Unix file systems to maintain consistency without journaling by ordering writes to prevent inconsistency.