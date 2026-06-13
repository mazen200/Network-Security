Because of the DES vulnerability to brute-force attacks, it is replaced by stronger encryption schemes.
-  One approach is to design a **completely new algorithm** such as AES
-  Another alternative is to use **multiple encryption with DES and multiple keys**.

### Double Encryption
![[Pasted image 20260613184745.png]]
-  For 2DES, this scheme involves a key length of 56 * 2 = 112 bits
	➔Requires for brute force attack:
		➢ Worst-case: $2^{112}$ operations
		➢ on average: $2^{111}$ operations
-  However, The *meet-in-the-middle attack* makes it easier.
-  The meet-in-the-middle (MITM) attack is a *known-plaintext* *attack* that targets encryption schemes relying on multiple encryption operations.
-  It does not depend on any particular property of DES but will work against any block encryption cipher
> [!NOTE] For Double Encryption
> For a block cipher with a k-bit key, a known- plaintext attack defeats double encryption using on the order of 2k operations and 2k storage.

![[Pasted image 20260613185945.png]]

---
### Triple Encryption
This approach is commonly referred to as 3DES, or Triple Data Encryption Algorithm (TDEA).
-  There are two versions of 3DES:
	-  3DES with two keys
	- 3DES with three keys.
![[Pasted image 20260613190227.png]]
#### Known-Plaintext Attack on 3DES with 2 keys
Given a known pair $(P, C)$ , the attack proceeds as follows:
1. Obtain n $(P , C )$ pairs. This is the known plaintext. Place these in a table (Table 1) sorted on the values of $P$.
2. Pick an arbitrary value a for $A$, and create a second table with entries defined as follows:
	▪ For each of the 256 possible keys $K_1 = i$, calculate the plaintext value $P$, such that $P_i = D(i, a)$
	▪ For each Pi that matches an entry in Table 1, create an entry in Table 2 consisting of the $K_1$ value and the value of B that is produced for the $(P, C)$ pair from Table $1 ➔ B_j = D(i, C_i)$
	▪ Sort Table 2 on the values of $B$.
	▪ We now have a number of candidate values of K1 in Table 2 and want to search for a value of K2.
3. For each of the 256 possible keys $K_2 = j$, calculate the second intermediate value for our chosen value of $a : B_j = D(j, a)$
4. At each step, look up $B_j$ in Table 2. If there is a match, then the corresponding key i from Table 2 plus this value of j are candidate values for the unknown keys $(K_1, K_2)$. 
5. Test each candidate pair of keys (i, j) on a few other plaintext ciphertext pairs.
	- If a pair of keys produces the desired ciphertext, the task is complete.
	- If no pair succeeds, repeat from step 1 with a new value of a.