With the increasing use of highly constrained devices (i.e., especially in the IoT), it is required to develop new stream ciphers that:
**– Take up minimal memory**
**– Are highly efficient**
**– have minimal power consumption requirements**
> Feedback Shift Registers are widely used for efficient hardware-based stream cipher design.

![[Pasted image 20260613213432.png]]
![[Pasted image 20260613213930.png]]
### Linear Feedback Shift Register LFSR
![[Pasted image 20260613214009.png]]
#### Example
![[Pasted image 20260613214028.png]]
![[Pasted image 20260613214040.png]]
### Nonlinear Feedback Shift Registers NFSR
![[Pasted image 20260613214131.png]]
![[Pasted image 20260613214150.png]]
****

>[!Note] 
>-  For an n-bit Linear Feedback Shift Register (LFSR) 
>	 *Maximum Period of LFSR = 2n − 1*
>- In LFSR, The all-zero state is invalid (it loops forever)
>- For an n-bit Nonlinear Feedback Shift Register,
>		 *Maximum Period of NFSR= 2n*
>		 ➢ Because feedback is nonlinear, it can escape the zero state
>		 ➔ **modern ciphers like Grain use both: LFSR and NFSR toensure a long period and provides the cryptographic "confusion."**