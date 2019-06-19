# Architecture

Stack vs Memory-to-Memory vs Register computation

So far I've created a stack machine with multiple linear memories per process.
If a process couldn't have several linear memories, it would be much more difficult to specify what happens when a subprocess (which is instantiated from the linear memory) allocates more memory itself.

A first version of the VM required that the invoked subprocess was located at the end of the single linear memory, so that the parent process simply increased with the subprocess in size. But this requires a lot of shuffling and reallocation, which is very inefficient.

In the case of multiple linear memories, access to subprocess memories would be comparatively rare (mostly limited to parameter insertion and result retrieval), so they wouldn't need to occupy the cache most of the time.  

What is yet unexplored is the cost of reallocation and how it would affect the gas price of the ALLOC/DEALLOC instructions. The VM itself would have to realloc() growing memories, which could have highly variable and unpredictable costs.

Another issue with multiple memories is the required additional instruction parameter on memory access. An implicit register (in previous versions, called Memory Pointer, MP) could store parameter to reduce code size at the expense of memory context switch latency.

In case of lower-level optimization, these design decisions may appear to be mere choices between different higher-level semantics, with the same lower-level resource characteristics. It has to be seen how much the underlying substrate changes the instruction cost table.

Perhaps even the gas cost table should be dynamically modifiable by the root process.
