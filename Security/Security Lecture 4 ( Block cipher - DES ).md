
>[!TIP] Remember:
>-  **Confusion** is intended to make the relationship between the key and ciphertext as complex as possible. 
>- **Diffusion** refers to spreading the influence of one plaintext symbol over many ciphertext symbols.
#### What is Block Cipher?
-  A block of plaintext is treated as a whole and used to produce a ciphertext block of equal length.
-  Typically, a block size of *64* or *128* bits is used.
-  For the encryption to be **reversible** (i.e., for decryption to be possible with **no data loss**), each plaintext block must produce a **unique** ciphertext block.
#### Feistel Cipher
 Feistel proposed that the ideal block cipher utilizes the concept of a product cipher
-  Consists two or more simple ciphers in sequence so that the result is cryptographically stronger than any of **the** component ciphers.
    -> **Confusion & Diffusion Concepts.**
---
>[!Note] Remember:
In a strongly ideal cipher:
➢ all statistics of the ciphertext are **independent** of the particular key used. 
➢ **statistical patterns in plaintexts are hidden** (each plaintext digit affect the value of many ciphertext digits)

![[Pasted Image 20260613002223_255.png]]

---
#### Feistel Cipher Parameters
1. *Block size*
	 Larger block sizes mean greater security but reduced encryption/decryption speed for a given algorithm
2. *Key size*
	Larger key size means greater security but may decrease encryption/decryption speeds
3. *Number of rounds*
	A single round offers inadequate security, but multiple rounds offer increasing security
4. *Subkey generation algorithm*
	Greater complexity in this algorithm should lead to greater difficulty of cryptanalysis
5. *Round function F*

----
#### DES Features
– Block size = *64* bits
– Key size = *56* bits (in reality, 64 bits, but 8 are used as parity-check bits for error control)
– Number of rounds = *16*
– *16 intermediary keys (Subkeys) , each 48 bits*
![[Pasted image 20260613003415.png]]

> [!Notes] 
> - The **S-boxes** provides the real **confusion** in DES 
> - **DES uses 8 different S-boxes**, each with *6-bit input* and *4-bit output*.
> - The **S-boxes** are the most crucial elements of DES because they introduce a **non-linearity** to the cipher $S a ⊕ S b ≠ S (a ⊕ b)$
> - DES has **4 weak keys** and **6 pairs of semi-weak keys**.
> - **Weak Key**: A key K such that $E_k(E_K(x)) = x$
> 	- After parity drop operation, consists either of all 0s, all 1s, or half 0s and half 1s.
> 	- Makes the same sub-key to be generated in more than one round
> - **Semi-weak Key**:
> 	-  pair of DES semi-weak keys is a pair $(K_1,K_2)$ with $E_{K1} (E_{K2} (x)) = x$.
> 	- creates only two different round keys and each of them is repeated eight times.
> 	- the round keys created from each pair are the same with different orders.
> 

**Shifting in Key generation**

| Round       | Shift    |
| ----------- | -------- |
| 1, 2, 9, 16 | One bit  |
| otherwise   | Two bits |

---
DES Structure
![[DES.restored]]
#### DES Properties & Strength
 The Use of 56-Bit Keys
- With a key length of 56 bits, there are 256 possible keys, which is ~ 7.2 X 1016 keys
-  A brute-force attack appears impractical while using a single machine performing one DES encryption per microsecond that would take more than a thousand years to break the cipher.
-  If multiple PCs work in parallel, the time is drastically shortened.
-  Today’s supercomputers can find a key in about an hour.
> Key sizes of *128 bits* or greater are effectively *unbreakable* using simply a brute-force approach.
##### Average Time Required For Exhaustive Key Search
![[Pasted image 20260613010554.png]]

---
#### Avalanche effect 
A small change in either the plaintext or the key produces a significant change in the ciphertext.
 	-> *If only one bit changed in plaintext/key, about half of the bits in the ciphertext would differ .*
These are two formal cryptographic properties used to measure the "strength" of the Avalanche Effect
1. **Strict Avalanche Criterion (SAC)**: If you flip exactly one input bit, each output bit must change with a probability of exactly 50%.”
	➢ every specific output bit is equally sensitive to every specific input bit.
	➢ Ensures diffusion
2. **Bit Independence Criterion (BIC)**: When any input bit is flipped, the changes in the output bits should be independent of one another.
	➢ No patterns (correlations) in the ciphertext