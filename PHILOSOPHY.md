# Philosophy

## Machine cooperation, the very big picture

In distributed systems, shared beliefs, laws, systems of accountability and behavioral constraints enable large scale cooperation. Humans have this, digital systems do not have this yet. In most cases, humans are still required to mediate between programs. Cooperation can only be achieved if systems can rely on each other, or if trust is not required in the first place. Sufficient security is a fundamental requirement for any type of cooperation.

There are many strategies to limiting trust, including making the behavior of a system more predictable (deterministic), limiting access to internal and external resources (sandboxing) and having common, formally verifiable standards (well defined interfaces and protocols).

Machine cooperation is desirable. Think of all the devices you own. Right now, you can use only one at a time. While one is computing for you, the others are mostly idle. It's time to change that. Not just for economic reasons, but because the concept of programs cooperating in your best interest, and jumping processes between machines are pretty cool.

## The principle of least authority

Very few languages actually adhere to the security principle of least authority ('POLA' - grant processes and their constituents as many permissions as necessary, but as few as possible). This leads to security disasters such as the recent NPM malware incident.

In a few decades, tiny processors will be everywhere. We'll better have appropriate mechanisms that make them secure. Even better, with the right substrate, they might even be able to manage themselves some day! Capability Security shows how to make such systems scale securely. And the Agoric Papers detail market based cooperation mechanisms that could be build on them. This system aims to follow the POLA principle as close as possible. Here, you can import a library and attenuate its authority by giving it only the necessary resources. It is of course only one attempt, but I hope there will be many more.
