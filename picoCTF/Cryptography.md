# 1. buffer overflow 0

>Can you abuse the oracle?
An attacker was able to intercept communications between a bank and a fintech company. They managed to get the message (ciphertext) and the password that was used to encrypt the message.
After some intensive reconassainance they found out that the bank has an oracle that was used to encrypt the password and can be found here nc titan.picoctf.net 59603. Decrypt the password and use it to decrypt the message. The oracle can decrypt anything except the password.

## Solution:

- I connected to server using the netcat connection given and understood how the oracle was doing the encryption and the decryption of given input. I planned on indirectly making the oracle decrypt the password.enc then using the python program to run openssl and pass the decrypted password to decrypt the secret.enc to get the flag.

```python
from subprocess import run, PIPE  
  

with open("password.enc", "r") as f:  
	c = int(f.read())   
  
print(f"c = {c}\n")  
 

m1 = input("Enter encrypting data: ")  
m1_bytes = bytes(m1, "utf-8")  
m1_int = ord(m1_bytes) 
  
print(f"Have the oracle encrypt this message (m1): {m1}\n")  
c1 = int(input("Enter ciphertext from oracle (c1 = E(m1)): "))  
print("\n")  
 

c2 = c * c1  
print(f"Have the oracle decrypt this message (c2 = c * c1): {c2}\n")  
  
m2 = int(input("Enter decrypted ciphertext as HEX (m2 = D(c2): "), 16)  
print("\n")  
 

m_int = m2 // m1_int  
m = m_int.to_bytes(len(str(m_int)), "big").decode("utf-8").lstrip("\x00")
print(f"Password (m = m2 / m1): {m}\n")  
  
print("-" * 50)      
 
# Decrypt the secret and print it
res = run(["openssl", "enc", "-aes-256-cbc", "-d", "-in", "secret.enc", "-pass",  
f"pass:{m}"], stdout=PIPE, stderr=PIPE, text=True)  
print(res.stdout)
```

the netcat connection :

<img width="1463" height="533" alt="image" src="https://github.com/user-attachments/assets/dd6f6ad0-d160-42a8-aea7-342f3630a5a4" />

the python code execution in the terminal
<img width="1477" height="607" alt="image" src="https://github.com/user-attachments/assets/527b742c-703f-40be-b203-8e53504429d6" />


## Flag:

```
picoCTF{su((3ss_(r@ck1ng_r3@_60f50766}
```

## Concepts learnt:

- i learned about the concept of rsa oracle and how it can be exploited by the atttackers to get the encryption info leaked from it.

## Notes:

- i was directly trying to get the password.enc decrypted by the oracle but it kept failing.

## Resources:

-  (https://en.wikipedia.org/wiki/Padding_oracle_attack)

