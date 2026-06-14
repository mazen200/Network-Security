# Elliptic Curve Cryptography ECC
▪ ECC is the *newest* member of the three families of public-key algorithms
▪ ECC provides the same level of security as RSA or discrete logarithm systems with considerably **shorter keys**               
		➔ More efficient

![[Pasted image 20260614174612.png]]

> [!Note] Important
> $y^2 ≡ x^3 + a  x + b \mod p$
> Condition : $4 a^3 + 27 b^2 ≠ 0 \mod p$
> 
> ![[Pasted image 20260614174915.png]]
> - The discrete logarithm problem for elliptic curves i**s to find an integer x for which Q = xR,** where R and Q are two given points on an elliptic curve E modulo p.



![[Pasted image 20260614175303.png|581]]
![[Pasted image 20260614175725.png]]
###  Elliptic Curve Diffie–Hellman (ECDH) KeyExchange
![[Pasted image 20260614181344.png|613]]
![[Pasted image 20260614181357.png]]
Example 
![[Pasted image 20260614182736.png|482]]
![[Pasted image 20260614182753.png]]
![[Pasted image 20260614182802.png|482]]