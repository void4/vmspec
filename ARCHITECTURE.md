# Architecture

Stack vs Memory-to-Memory vs Register computation

So far I've created a stack machine with multiple linear memories per process.
If a process couldn't have several linear memories, it would be much more difficult to specify what happens when a subprocess (which is instantiated from the linear memory) allocates more memory itself. A first version of the VM required that the invoked subprocess was located at the end of the single linear memory, so that the parent process simply increased with the subprocess in size. But this requires a lot of shuffling and reallocation, which is very inefficient. In the case of multiple linear memories, access to subprocess memories would be comparatively rare (mostly limited to parameter insertion and result retrieval), so they wouldn't need to occupy the cache most of the time.  
