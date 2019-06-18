## Design considerations

Validation of a process image should be possible in linear time O(N), to prevent validation attacks.

The time/gas and space accounting mechanisms require that each operation has sufficiently similar resource characteristics each time it is invoked. If operations behaved differently depending on their order, enclosing operations or number of invocations, the accounting mechanism would be inaccurate.

This excludes "high-level" operations or those with a variable type or number of operands.


Recursive sandboxing should incur no overhead, otherwise the RECURSE operation would have to be priced differently too, depending on the process tree depth.

From this follows that the VM must be stateless (a pure "step" function, from process image to process image). The process metadata should be ideally structured such that resuming a snapshot would require constant time, instead of having to traverse a list of pointers down to the current active process.

Optimizations are possible, but should be semantically identical and should not further impair worst case behavior.

Universally consistent accounting requires that the VM be fully deterministic and therefore single-threaded. This property allows for reproducible and thereby multi-party verifiable computation.

Any interface to external functions should be platform independent.

It should be possible to limit subprocesses to time and space and prevent access to any communication channels, only this would allow uses like genetic programming and optimization to be done securely.

A process should be able to create a subprocess from linear memory and recover a linear memory image if it suspends and returns control.

Process images should be as small as possible in order to be portable and enable mobile agents. This implies that calls to external systems (ideally, other agents) should provide high level functionality.


