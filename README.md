# vmspec - rarVM

rarVM is a a resource aware, recursively sandboxable virtual machine built to simultaneously have these properties:

* fine grained control of process-internal resources (cpu time/cycles, memory usage)
* control of access to process-external resources (filesystem, networking)
* doing the above recursively, to securely sandbox libraries from each other
* the platform-independent transfer of process state (mobile agents, "jumping processes")

A few examples of what you can do with it are here:
https://esolangs.org/wiki/RarVM

[Philosophy](PHILOSOPHY.md)

[Considerations](CONSIDERATIONS.md)

[Possibilities](POSSIBILITIES.md)

[Architecture](ARCHITECTURE.md)

[Todo](TODO.md)
