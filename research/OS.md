# Logical address
the address at which an item appears to reside from the perspective of an executing application program

logical address is different from the physical address due to the operation of an address operator or mapping function.

The physical address of memory banks may be mapped to different logical address for  various purposes.

In **Virtual Memory**, there may actually not be any physical memory mapped to a logical address until an access is attempted. The access triggers special functions of the operating system which reprogram the MMU to map the address to some physical memory, perhaps writing the old contents of that memory to disk and reading back from the disk what the memory should contain at the new logical address. In this case, the logical address may be referred to as a **virtual address**.

**Virtual address** is the result of **Virtual Memory**
