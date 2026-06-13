**Requirements of Random Numbers**
![[Pasted image 20260613192328.png]]
- A random bit generator is a device or algorithm which outputs a sequence of statistically independent and unbiased binary digits.
-  There are two main strategies for generating random bits/numbers:
	1. True Random Number Generators (TRNGs):
		- Non-deterministic
		- Using some physical source
	2. Pseudorandom Number Generators (PRNGs)
		- Deterministic.
		- Using an algorithm.
![[Pasted image 20260613192458.png]]
#### True Random Bit Generators (TRNGs)
 - A true random bit generator falls in one of two categories:
	1. Hardware-based generators:
		• Use the randomness which occurs in some physical phenomena.
		• Examples:
			– Thermal noise from a semiconductor or resistor.
			– Sound from a microphone or video input from a camera.
	2. Software-based generators: Some processes such as:
		• Elapsed time between keystrokes or mouse movement;
		• Content of input/output buffers.
		• Operating system values such as system load and network statistics.
- Designing a TRNG that is free of biases and correlations is a **difficult and expensive** task.
#### Pseudorandom Number Generators (PRNGs)
![[Pasted image 20260613193049.png]]
##### PRNG Requirements
The basic requirement when a PRNG or PRF is used for a cryptographic application is that it is hard to determine pseudo-random stream if the adversary doesn’t know seed (but knows algorithm)
▪ Randomness
	– Generated bit stream appear random even though it is deterministic
▪ Unpredictability
	– Forward and backward unpredictability
▪ Seed characteristics
	– Seed must be secure and unpredictable
	– Use TRNG to generate the seed

----
##### LCG
![[Pasted image 20260613193313.png]]
>[!Warning] LCG is not cryptographically secure.
If the attacker knows any three subsequent output symbols of the PRNG, he can get the values of a & c.
➔ The attacker can get the entire stream

---
##### Blum Blum Shub (BBS)
![[Pasted image 20260613193608.png]]

---
##### PRNG Mechanisms Based On Block Ciphers
![[Pasted image 20260613194311.png]]
![[Pasted image 20260613204257.png]]
##### NIST CTR-DRBG Parameters
- Output block length (outlen)
- Key length (keylen)
- Seed length (seedlen) = outlen + keylen
- Reseed interval :The maximum number of output blocks generated before updating the algorithm with a new seed.
![[Pasted image 20260613204557.png]]
