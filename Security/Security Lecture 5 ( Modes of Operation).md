#### Modes of Operation
- Electronic Codebook (ECB)
- Cipher Block Chaining (CBC)
- Cipher Feedback (CFB)
- Output Feedback (OFB)
- Counter (CTR)
#### Design Goals of Modes
- **Confidentiality** (hide plaintext)
- **Randomization** (same plaintext ≠ same ciphertext)
- **Parallelism** (Can we process multiple blocks at once?)
- **Random access** (Ability to decrypt any block without requiring you to process every previous block)
- **Error propagation control** (What happens if one bit of a ciphertext block is corrupted during transmission?)
### 1. Electronic Codebook ECP
![[Pasted image 20260613025524.png]]
**Characteristics of ECP :** 
1. Simple
2. Parallelizable
3. No Chaining ➔ No Error propagation
4. No randomness: Leaks data patterns (i.e., Identical plaintext blocks → identical ciphertext blocks)
➔ For this reason, the ECB mode is not recommended for messages longer than one block
---
### Cipher Block Chaining CBC
 We can define CBC mode as follows.
- Encryption: $C_j = E(K, (C_{j-1} ⊕ P_j ))$
- Decryption: $P_j = C_{j-1} ⊕ D(K, C_j )$
![[Pasted image 20260613025737.png]]
- The initialization vector (IV) must be known to both the sender and receiver but be unpredictable by a third party.
**Properties of the CBC :**
-  *Randomized encryption*: Identical plaintext blocks results in different ciphertext.
	➔ hides patterns
-  *Chaining dependencies*: Proper encryption/decryption of a correct block requires a correct encryption/decryption of a preceding ciphertext block.
	➔ *Not parallelizable* ; No random access
-  *Error propagation*: A single bit error in ciphertext block $c_j$ affects decryption of blocks $c_j$ and $c_{j+1}$
---
> [!Note] It is possible to convert a block cipher into a stream cipher, using one of the following three modes:
> 1. Cipher feedback (CFB) mode
> 2. Output feedback (OFB) mode
> 3. Counter (CTR) mode.
> -  A stream cipher eliminates the need to pad a message to be an integral number of blocks.
> -  If a character stream is being transmitted, each character can be encrypted and transmitted immediately

---
### 3. Cipher Feedback CFB
![[Pasted image 20260613030733.png]]
![[Pasted image 20260613030748.png]]
**Properties of CFP :**
-  Does it conform to the typical construction of a stream cipher? NO
-  Chaining ? YES
-  Error Propagation ? N/S 
- --
### Output Feedback OFB
![[Pasted image 20260613031450.png]]
![[Pasted image 20260613031555.png]]
**Properties Of OFB :**
-  The IV must be nonce. Why? 
	A nonce means a value that is **never reused** with the same key.

	In OFB, the IV and key generate the entire keystream. If the same IV is reused with the same key, the same keystream will be generated again.
	
-  Does OFB have the structure of a typical stream cipher? YES
-  Chaining dependencies?Yes, there is chaining, But the first step (generating stream key ) can be preproccessed.
- Error propagation? NO
---
### Counter CTR
![[Pasted image 20260613032457.png]]**Advantages of CTR**
1. *Simplicity*
2. *Efficiency*: Both encryption and decryption are fully parallelizable.
3. *Preprocessing*: You can compute the "key stream" E(K , Counter) before the plaintext even arrives.
4. *Random access*: You can decrypt block 100 without decrypting blocks 1–99

![[Pasted image 20260613205024.png]]