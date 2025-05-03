Operating Systems Notes and Question Bank for Exam Preparation
These notes are designed for an Indian college Operating Systems exam, covering File Management, Storage Management, Disk Scheduling, Free Space Management, RAID, Swap Space, and Protection. They are detailed yet concise, merging related content from the provided PDF to avoid repetition. Each topic includes explanations, examples, and visualizations, with a question bank for 4-mark and 6-8-mark questions to aid revision for a 40-mark paper (4 questions of 4 marks, rest MCQs).
1. File Management
File Management encompasses how operating systems handle files, including their creation, access, organization, and protection. It’s a critical topic, often tested in exams due to its foundational role in OS.
File Concepts

Definition: A file is a logical storage unit containing related information, abstracting physical storage (e.g., disks) for user convenience.
Purpose: Enables data storage, retrieval, and manipulation. Files are necessary to write data to disk, providing structure and metadata.
Data Types: Numeric, alphabetic, alphanumeric, binary, text, multimedia (e.g., images, videos), and program code (source or executable).
Example: A .txt file stores text, while a .jpg file stores an image, each with specific handling by the OS.

File Attributes

Definition: Metadata describing a file’s properties, stored in the directory structure.
Key Attributes:
Name: Human-readable identifier (e.g., report.txt).
Identifier: Unique tag (e.g., inode number in Unix).
Type: Indicates purpose (e.g., text, executable).
Location: Disk address or pointer.
Size: Current size in bytes.
Protection: Access permissions (e.g., read, write).
Timestamps: Creation, modification, access times.


Example: For document.pdf, attributes include its name, size (e.g., 2 MB), and permissions (e.g., read-only for others).

File Operations

Definition: Actions performed on files, managed by the OS.
Key Operations:
Create: Allocates space and adds a directory entry.
Write: Modifies data, updates file size.
Read: Retrieves data, moves read pointer.
Reposition (Seek): Moves file pointer without I/O.
Delete: Removes file, frees space.
Truncate: Clears content, retains attributes.
Append: Adds data to the end.
Open/Close: Manages access via the open-file table.


Open-File Table: Tracks open files, storing file pointers, access modes, and open counts.
Example: Opening file.txt adds it to the open-file table with a pointer to track the current read/write position.

File Types and Structures

Types: Executable (.exe), source code (.c), text (.txt), multimedia (.mp4), etc.
Structures:
Unstructured: Sequence of bytes (e.g., text files).
Structured: Defined format (e.g., database records).


Example: A .txt file is unstructured, while a database file has a structured format with records.

Access Methods

Sequential Access: Data accessed in order (e.g., tape drives).
Operations: read next, write next, reset.


Direct Access: Random access to any block (e.g., hard disks).
Operations: read n, write n, seek to n.


Indexed Access: Uses an index block with pointers to data blocks for faster retrieval.
Example: Sequential access for a log file, direct access for a database record.

Directory Structures

Single-Level Directory: One directory for all files.
Pros: Simple.
Cons: Naming conflicts, no grouping.


Two-Level Directory: Each user has a directory.
Pros: Reduces naming conflicts, faster searching.
Cons: Limited grouping.


Tree-Structured Directory: Hierarchical structure with subdirectories.
Pros: Efficient searching, grouping capability.
Example: /home/user/docs/report.txt.


Acyclic-Graph Directory: Allows shared files/directories without cycles.
Pros: Supports collaboration.
Cons: Complex link management.


Diagram:Root
├── User1
│   ├── File1.txt
│   └── Docs
│       └── Report.pdf
└── User2
    └── File1.txt (shared)



File System Mounting and Sharing

Mounting: Attaches a file system to a directory (mount point), making it accessible.
Example: Mounting a USB drive at /mnt/usb.


Sharing: Allows multiple users to access files.
Multi-User Systems: Uses user/group IDs for permissions.
Remote Sharing: Via protocols like NFS (Unix) or CIFS (Windows).
Consistency Semantics: Defines how updates are visible (e.g., UFS: immediate; AFS: after close).



Protection in File Systems

Definition: Controls access to files using permissions and access control.
Unix Permissions: Read (r), write (w), execute (x) for owner, group, others.
Example: rwxr-xr-- (owner: rwx, group: rx, others: r).


Windows ACLs: Fine-grained access control lists for specific users/groups.
Principle of Least Privilege: Grant minimal necessary access.
Setuid/Setgid: Allow programs to run with owner’s privileges.
Example: chmod 755 script.sh sets executable permissions for all, but only the owner can modify it.

Question Bank for File Management
4-Mark Questions

What are the key attributes of a file, and why are they important?

Answer: Key attributes include name (human-readable identifier), identifier (unique tag), type (e.g., text, executable), location (disk address), size (bytes), protection (permissions), and timestamps (creation/modification). They are crucial for managing files, enabling the OS to locate, secure, and track file usage. For example, permissions ensure only authorized users access confidential.txt.


Explain the difference between sequential and direct access methods with examples.

Answer: Sequential access reads/writes data in order, like a tape drive playing a playlist sequentially. Direct access allows jumping to any block, like a hard disk accessing a database record instantly. Sequential is simpler but slower for random access, while direct is faster but complex.


Describe the role of the open-file table in file operations.

Answer: The open-file table tracks open files, storing file pointers (current position), access modes, and open counts. It ensures efficient read/write operations and manages concurrent access. For example, when file.txt is opened, its details are added to the table, and a descriptor is returned.


What are the advantages of a tree-structured directory over a single-level directory?

Answer: A tree-structured directory allows hierarchical organization, enabling efficient searching and grouping (e.g., /home/user/docs). Unlike a single-level directory, it avoids naming conflicts and supports subdirectories, making it scalable but more complex.



6-8-Mark Questions

Discuss the various directory structures in file systems, highlighting their pros and cons.

Answer: Directory structures organize files for efficient access:
Single-Level: One directory for all files. Pros: simple. Cons: naming conflicts, no grouping.
Two-Level: User-specific directories. Pros: reduces conflicts, faster search. Cons: limited grouping.
Tree-Structured: Hierarchical with subdirectories. Pros: efficient, supports grouping (e.g., /home/user/docs). Cons: complex path management.
Acyclic-Graph: Shared files/directories. Pros: collaboration-friendly. Cons: link management complexity.
Example: A tree structure allows organizing project files under /projects/team1, unlike a single-level directory causing name clashes.




Explain file system mounting with an example. Why is it necessary?

Answer: Mounting attaches a file system to a directory (mount point), integrating it into the directory tree. For example, mounting a USB drive at /mnt/usb makes its files accessible via that path. It’s necessary to access external or new file systems, ensuring seamless integration. Consistency checks during mounting prevent data corruption, making it critical for system reliability.


Describe protection mechanisms in Unix file systems, including permissions and setuid.

Answer: Unix uses permissions (read, write, execute) for owner, group, and others, set via chmod (e.g., rwxr-xr--). Directories require execute permission for access. Setuid allows programs to run with the owner’s privileges, like passwd updating system files. These mechanisms ensure secure access control, preventing unauthorized modifications while enabling necessary operations.



2. Storage Management
Storage Management handles disk organization, performance, and reliability, a frequently tested topic due to its practical importance.
Disk Structure and Partitions

Disk Structure:
Physical Layout: Platters with tracks and sectors, organized into cylinders. Disk heads on arms read/write data.
Performance Metrics: Seek time (arm movement), rotational latency (sector alignment), transfer rate (data flow).


Partitions:
Definition: Logical disk divisions for organization.
Types: Raw (no file system, e.g., swap space) or formatted (with file system, e.g., NTFS).
Volumes: Partitions with file systems, tracked in a volume table of contents.
Example: A disk with a Windows partition and a data partition, mounted at boot.



RAID (Redundant Array of Independent Disks)

Definition: Combines multiple disks for reliability and performance.
Levels:
RAID 0: Striping, no redundancy. Fast but risky.
RAID 1: Mirroring, duplicates data. Reliable but costly.
RAID 5: Distributed parity, balances speed and redundancy.
RAID 10: Striping + mirroring, high performance and reliability.


Example: RAID 5 for a database server, ensuring data recovery if one disk fails.
Diagram:RAID 5:
Disk1: Data1 | Parity2 | Data3
Disk2: Data2 | Data4  | Parity3
Disk3: Parity1 | Data5 | Data6



Disk Scheduling Algorithms

Purpose: Minimize seek time, maximize bandwidth for disk I/O requests.
Algorithms:
FCFS: Serves requests in order. Simple, high seek time.
SSTF: Serves closest request next. Efficient but risks starvation.
SCAN: Moves head end-to-end, servicing requests. Fair, systematic.
C-SCAN: Like SCAN, but returns to start without servicing on return.


Example (Queue: 98, 183, 37, 122, 14, 124, 65, 67; Head at 53):
FCFS: Total movement = 640 cylinders.
SSTF: Order: 37, 65, 67, 98, 122, 124, 14, 183. Total = 376 cylinders.
SCAN: Order: 65, 67, 98, 122, 124, 183, 37, 14. Total = 322 cylinders.
C-SCAN: Order: 65, 67, 98, 122, 124, 183, 14, 37. Total ≈ 338 cylinders.


Visualization (SSTF):Head at 53
Step 1: Move to 37 (16 cylinders)
Step 2: Move to 65 (28 cylinders)
Step 3: Move to 67 (2 cylinders)
...



Question Bank for Storage Management
4-Mark Questions

What is the purpose of disk partitioning?

Answer: Partitioning divides a disk into logical sections for organization, allowing multiple OSes or data separation. For example, one partition for Linux and another for data ensures isolated management and protection.


Explain the difference between RAID 0 and RAID 1.

Answer: RAID 0 stripes data across disks for high performance but no redundancy, risking data loss if a disk fails. RAID 1 mirrors data on two disks, ensuring reliability but doubling storage needs.


Describe the FCFS disk scheduling algorithm.

Answer: FCFS serves disk requests in arrival order, simple but inefficient due to high seek times. For example, requests at cylinders 98, 183, 37 from head at 53 result in 276 cylinders moved for three requests.


Why is RAID 5 preferred for large data storage?

Answer: RAID 5 distributes parity across disks, balancing performance and redundancy. It allows data recovery if one disk fails, using less space than RAID 1, ideal for databases.



6-8-Mark Questions

Compare SSTF and SCAN disk scheduling algorithms with an example.

Answer: SSTF serves the closest request, reducing seek time but risking starvation. SCAN moves the head systematically, ensuring fairness. For queue 98, 183, 37, 122, 14, 124, 65, 67 (head at 53), SSTF moves 376 cylinders (37, 65, 67, …), while SCAN moves 322 cylinders (65, 67, 98, …). SCAN is better for heavy loads due to less starvation.


Explain RAID levels 1, 5, and 10, highlighting their use cases.

Answer: RAID 1 mirrors data for high reliability, used in critical systems. RAID 5 uses distributed parity for balanced performance/redundancy, ideal for large databases. RAID 10 combines striping and mirroring for speed and reliability, used in high-performance applications like video editing.


Solve: Calculate total head movement for SSTF with queue 98, 183, 37, 122, 14, 124, 65, 67, head at 53.

Answer: SSTF serves closest requests:
53 to 37: 16 cylinders
37 to 65: 28
65 to 67: 2
67 to 98: 31
98 to 122: 24
122 to 124: 2
124 to 14: 110
14 to 183: 169
Total = 376 cylinders.





3. Disk Space Allocation and Free Space Management
This topic is crucial for understanding how files are stored and disk space is reused, often tested with numerical or conceptual questions.
Allocation Methods

Contiguous Allocation:
File occupies consecutive blocks.
Pros: Fast sequential/direct access.
Cons: External fragmentation, needs compaction.


Linked Allocation:
File as a linked list of blocks, each pointing to the next.
Pros: No external fragmentation, easy growth.
Cons: Slow random access, pointer overhead.


Indexed Allocation:
Index block stores pointers to data blocks.
Pros: Direct access, no fragmentation.
Cons: Index block overhead.


Example: For a 10-block file, contiguous allocation uses blocks 100-109; linked allocation chains scattered blocks; indexed allocation uses an index block pointing to data blocks.
Visualization (Indexed Allocation):Directory Entry -> Index Block
                   ├── Block 100
                   ├── Block 150
                   └── Block 200



Free Space Management Techniques

Bit Vector: Bitmap where 1 = free, 0 = allocated.
Pros: Simple, efficient for finding free blocks.
Cons: Large memory for big disks.


Linked List: Chain of free blocks.
Pros: No fragmentation.
Cons: Slow due to I/O.


Grouping: First free block stores addresses of n free blocks.
Pros: Faster than linked list.
Cons: Complex management.


Counting: Tracks contiguous free blocks with address and count.
Pros: Efficient for contiguous allocation.
Cons: Overhead for tracking.


Example: Bit vector for blocks 2, 3, 4 free: 001110....

Question Bank for Disk Space Allocation and Free Space Management
4-Mark Questions

What is contiguous allocation, and what are its drawbacks?

Answer: Contiguous allocation stores a file in consecutive disk blocks, offering fast access. Drawbacks include external fragmentation and difficulty growing files, requiring compaction.


Explain the bit vector method for free space management.

Answer: A bit vector uses a bitmap where each bit represents a block (1 = free, 0 = allocated). It’s simple and efficient for finding free blocks but requires significant memory for large disks.


How does linked allocation differ from indexed allocation?

Answer: Linked allocation chains blocks with pointers, avoiding fragmentation but slowing random access. Indexed allocation uses an index block for direct access, but has overhead for small files.


What is the purpose of free space management in file systems?

Answer: Free space management tracks available disk blocks for allocation to new files or file growth, ensuring efficient space reuse when files are deleted.



6-8-Mark Questions

Compare contiguous, linked, and indexed allocation methods with examples.

Answer: Contiguous allocation stores files consecutively (e.g., blocks 100-109), offering fast access but causing fragmentation. Linked allocation chains blocks (e.g., 100->150->200), avoiding fragmentation but slowing random access. Indexed allocation uses an index block pointing to data blocks, enabling direct access but with overhead. Contiguous is best for static files, linked for dynamic growth, indexed for flexibility.


Explain free space management techniques, highlighting their suitability.

Answer: Bit vector is simple but memory-intensive, suitable for small disks. Linked list avoids fragmentation but is slow, good for sequential allocation. Grouping speeds up linked lists, ideal for moderate-sized disks. Counting optimizes contiguous allocation, best for systems with large free spaces. Choice depends on disk size and access patterns.


Solve: For a 5-block file using indexed allocation, describe the allocation process if blocks 10, 20, 30, 40, 50 are free.

Answer: The OS allocates an index block (e.g., block 5) and five data blocks (10, 20, 30, 40, 50). The index block stores pointers to these blocks. The directory entry points to block 5, enabling direct access to the file’s data.



4. Swap Space Management
Swap Space Management is less frequently tested but important for understanding virtual memory.
Overview

Definition: Disk space used as an extension of RAM for virtual memory, holding swapped-out pages when memory is full.
Purpose: Allows more processes to run than physical memory can support.
Implementation:
4.3BSD: Allocates swap space at process start for text and data segments.
Solaris 2: Allocates when dirty pages are swapped out.
Linux: Uses swap files or partitions, managed by swap maps (array of counters).


Example: A system with 4 GB RAM and 8 GB swap space can handle larger workloads by swapping inactive pages to disk.

Question Bank for Swap Space Management
4-Mark Questions

What is swap space, and why is it used?

Answer: Swap space is disk space used as virtual memory to store pages swapped out from RAM. It allows the system to run more processes than physical memory supports, enhancing multitasking.


How does Linux manage swap space?

Answer: Linux uses swap files or partitions, with swap maps tracking page slots (0 = free, non-zero = used). Multiple swap areas improve flexibility and performance.


What is the role of swap maps in swap space management?

Answer: Swap maps are arrays of counters tracking swap slot usage. A zero indicates a free slot, while a non-zero value shows how many processes map to a swapped page.


Why might a system run out of swap space?

Answer: A system may run out of swap space if too many processes demand memory, exhausting swap slots. Multiple swap areas can mitigate this issue.



6-8-Mark Questions

Explain swap space management in 4.3BSD and Solaris 2.

Answer: In 4.3BSD, swap space is allocated at process start for text and data segments, tracked by swap maps. Solaris 2 allocates swap space only when dirty pages are swapped out, writing file data to swap until a file system write is requested. This reduces unnecessary swaps, improving efficiency.


Discuss the advantages and challenges of using swap space.

Answer: Swap space allows running large workloads by extending RAM, supporting multitasking. Challenges include slower disk access compared to RAM and potential exhaustion of swap space, requiring multiple swap areas or memory optimization.


Solve: If a system has 4 GB RAM and 8 GB swap space, how does it handle a 10 GB process?

Answer: The system uses 4 GB RAM for active pages and swaps 6 GB to swap space. Swap maps track these pages, ensuring efficient allocation. If swap space fills, the system may slow down or crash, requiring additional swap areas.



5. Protection and Security
Protection and Security are vital exam topics due to their emphasis on system integrity and access control.
Protection Mechanisms

Definition: Controls access to resources (files, memory) to prevent unauthorized use.
Access Matrix: Rows (domains/users), columns (objects/files), entries (rights).
Access Control Lists (ACLs): Specify permissions per object (e.g., Windows NTFS).
Unix Permissions: rwx for owner, group, others.
Principle of Least Privilege: Minimal necessary access.
Setuid/Setgid: Programs run with owner’s privileges.

Security Threats and Defenses

Threats:
Confidentiality Breach: Unauthorized data access.
Integrity Breach: Unauthorized modification.
Availability Breach: Denial of service.


Defenses:
Cryptography: Encrypts data (e.g., SSL).
Authentication: Passwords, multi-factor.
Firewalls: Block unauthorized network access.


Example: A virus (threat) can be countered by antivirus software (defense).

Question Bank for Protection and Security
4-Mark Questions

What is the principle of least privilege in protection?

Answer: It ensures programs/users have only necessary privileges, minimizing damage from errors or attacks. For example, a user editing file.txt needs write permission only for that file.


Explain Unix file permissions with an example.

Answer: Unix permissions include read, write, execute for owner, group, others. rwxr-xr-- allows owner full access, group/others read and execute. Set via chmod 750 file.


What is an access control list (ACL) in file systems?

Answer: An ACL specifies permissions for specific users/groups on a file. In NTFS, an ACL might grant “Read” to User1 and “Full Control” to Admin, offering fine-grained control.


Name two security threats and their defenses.

Answer: Confidentiality breach (unauthorized data access) is countered by cryptography (e.g., SSL). Denial of service is mitigated by firewalls, blocking malicious traffic.



6-8-Mark Questions

Discuss the access matrix model for protection with an example.

Answer: The access matrix has domains (rows) and objects (columns), with entries defining rights (e.g., read, write). For example, User1 has read access to file1.txt and write to file2.txt. It supports dynamic access control but is complex to implement for large systems.


Explain how Unix and Windows handle file protection differently.

Answer: Unix uses rwx permissions for owner, group, others, set via chmod (e.g., rwxr-xr--). Windows NTFS uses ACLs, allowing specific permissions (e.g., “Modify” for User1). Unix is simpler, while Windows offers granular control, suitable for complex systems.


Describe security threats and defenses in operating systems.

Answer: Threats include confidentiality breaches (data theft), integrity breaches (data alteration), and denial of service. Defenses include cryptography for secure communication, authentication (passwords, multi-factor), and firewalls to block attacks. For example, SSL protects web data, while antivirus software counters viruses.



