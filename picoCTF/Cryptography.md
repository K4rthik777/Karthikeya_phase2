# 1.RSA oracle

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
-  (https://secgroup.dais.unive.it/wp-content/uploads/2012/11/Practical-Padding-Oracle-Attacks-on-RSA.html)

# 2.Custom encryption

>Can you get sense of this code file and write the function that will decode the given encrypted file content.
Find the encrypted file here flag_info and code file might be good to analyze and get the flag.


## Solution:

- I checked out the encryption code given and understood how it worked to encrypt.Then i created functions that reversed the effect of the original functiuon in the encryption process.

```python
from custom_encryption import is_prime, generator
 
 
def leak_shared_key(a, b):
    p = 97
    g = 31
    if not is_prime(p) and not is_prime(g):
        print("Enter prime numbers")
        return
    u = generator(g, a, p)
    v = generator(g, b, p)
    key = generator(v, a, p)
    b_key = generator(u, b, p)
    shared_key = None
    if key == b_key:
        shared_key = key
    else:
        print("Invalid key")
        return
 
    return shared_key
 
 
def decrypt(ciphertext, key):
    semi_ciphertext = []
    for num in ciphertext:
        semi_ciphertext.append(chr(round(num / (key * 311))))
    return "".join(semi_ciphertext)
 
 
def dynamic_xor_decrypt(semi_ciphertext, text_key):
    plaintext = ""
    key_length = len(text_key)
    for i, char in enumerate(semi_ciphertext):
        key_char = text_key[i % key_length]
        decrypted_char = chr(ord(char) ^ ord(key_char))
        plaintext += decrypted_char
    return plaintext[::-1]
 
 
if __name__ == "__main__":
    a = 94
    b = 21
    ciphertext_arr = [131553, 993956, 964722, 1359381, 43851, 1169360, 950105, 321574, 1081658, 613914, 0, 1213211, 306957, 73085, 993956, 0, 321574, 1257062, 14617, 906254, 350808, 394659, 87702, 87702, 248489, 87702, 380042, 745467, 467744, 716233, 380042, 102319, 175404, 248489]
    text_key = "trudeau"
    shared_key = leak_shared_key(a, b)
 

    semi_ciphertext = decrypt(ciphertext_arr, shared_key)
 

    plaintext = dynamic_xor_decrypt(semi_ciphertext, text_key)
 
    print(plaintext)
```

## Flag:

```
picoCTF{custom_d2cr0pt6d_8b41f976}
```

## Concepts learnt:

- i learned about how different python functions can be created to encrypt and decrypt data in many custom ways.

## Notes:

## Resources:

-  (https://www.geeksforgeeks.org/computer-networks/diffie-hellman-key-exchange-and-perfect-forward-secrecy/)

# 2.Custom encryption

>Can you get sense of this code file and write the function that will decode the given encrypted file content.
Find the encrypted file here flag_info and code file might be good to analyze and get the flag.


## Solution:

- I checked out the ciphertext file given and found that the given e value was a little too small than usual as the hint also suggested it.Then i found that such small value of e creates a chance for us to bruteforce the decryption by simply using a rsa decoder.So when i decrypted it in the online decoder it gave the flag.

<img width="1362" height="573" alt="image" src="https://github.com/user-attachments/assets/831680c1-da52-4fd8-afc0-2ae3e1baf759" />


## Flag:

```
picoCTF{n33d_a_lArg3r_e_d0cd6eae}
```

## Concepts learnt:

- i learned about how the value of e being so small cause the rsa encryption to so vulnerable.

## Notes:
- i tried to use python program as used in the previous challenges but it was becoming complicated as the cipher text and the N values are just too big. 

## Resources:

-  (https://en.wikipedia.org/wiki/RSA_cryptosystem)
