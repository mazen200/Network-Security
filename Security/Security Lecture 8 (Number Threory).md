#### Divisibility
![[Pasted image 20260613232824.png]]
-  **If $b | x$ and $b | y$, then $b| (mx + ny)$ for any integers $m, n$**

### Modular Arithmetic
-  If a is an integer and n is a positive integer, we define a mod n to be the remainder when a is divided by n
	➢ n is called the modulus
-  Two integers a and b are congruent modulo n if: 
	 (a mod n) = (b mod n), which is written as a ≡ b (mod n)
- Example: 23 ≡ 8(mod 5 )
	➢ Because 23 mod 5 = 3 and 8 mod 5 = 3
>[!NOTE] Symmetric Property
If a ≡ b mod n , then: b ≡ a mod n

![[Pasted image 20260613233520.png]]
![[Pasted image 20260613233539.png]]
##### Multiplicative Inverse & Division In Mod Space
![[Pasted image 20260613233800.png]]
Example for mod 8
![[Pasted image 20260613233829.png]]

>[!NOTE] ### Euclidean Algorithm 
> 
> $gcd(a, b) = gcd(b, a\mod b)$
 >$gcd(a, b) = gcd(|a|, |b|)$
 >$gcd(a, 0) = | a |$
 >
 
 
 ![[Pasted image 20260613234819.png]]
 ![[Pasted image 20260613234647.png]]
 ![[Pasted image 20260613234709.png]]

#### Extended Euclidean Algorithm 
- The extended Euclidean algorithm not only finds $gcd(a, b)$ but also finds integers x and y such that:
 			$ax + by = gcd(a, b)$
- Used to find **modular inverse** $a^{−1} \mod m$ when $gcd(m, a) = 1$
![[Pasted image 20260613235404.png]]
![[Pasted image 20260614000038.png]]

### Euler’s Totient Function, $φ(n)$
$φ(n)$: the number of positive integers less than n and coprime to n
>[!Note] Don't Forget
>-  $φ(1) = 1$
>-  For prime $p$, $φ (p) = p − 1$
>-  For primes $p$ and $q$, and $n = p × q$, $φ(n) = (p − 1) (q − 1)$
>- If $n = p^k$ (prime power): $φ (p^k) = p^k − p^{k−1}$
>	- Example: $φ(16) = φ(2^4) = 2^4 - 2^3 = 16 – 8 = 8$

>[!NOTE] ### Euler’s Theorem
>- for every $a$ and $n$ that are relatively prime: $a^{φ(n)} = 1(mod n)$
>- An alternate form is: $a^{φ(n +1)} = a (mod n)$
> ![[Pasted image 20260614003214.png]]

>[!NOTE] ### Fermat’s Theorem
>-  If $p$ is prime and $a$ is a positive integer not divisible by $p$ then:
	>		$a^{p−1} = 1(mod p)$
>-  An alternate form is: $a^p = a (mod p)$
> ![[Pasted image 20260614003441.png]]
> ![[Pasted image 20260614003734.png]]
> 
****
### Logarithms in Modular Arithmetic
![[Pasted image 20260614004158.png]]
![[Pasted image 20260614004959.png]]![[Pasted image 20260614005016.png]]
**Primitive Root**
![[Pasted image 20260614005226.png]]
#### Questions
![[Pasted image 20260614010143.png]]
