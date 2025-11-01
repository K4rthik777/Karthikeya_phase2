# 1. IQ Test

> let your input x = 30478191278.

wrap your answer with nite{ } for the flag.

As an example, entering x = 34359738368 gives (y0, ..., y11), so the flag would be nite{010000000011}.

<img width="1225" height="2176" alt="iqtest" src="https://github.com/user-attachments/assets/6ccfb3d7-b2f8-4895-8b6a-44e081d53183" />


## Solution:

- i converted the given number in the desc.txt into 36 bit binary number and entered each digit in the respective inputs in the logic gates circuit and solved to get the digits of the flag.

![WhatsApp Image 2025-10-31 at 23 24 50_9d3bd07c](https://github.com/user-attachments/assets/ae0e3a21-6f01-411f-ab20-f52e9f9361ca)


## Flag:
```
nite{100010011000}
```

## Concepts learnt:

- I learned the AND,OR,NOR,NAND,XOR, and XNOR gates with thier truth tables

## Notes:

- i just went on solving the logic gates with their correct truth tables.

## Resources:

-  (https://www.schoolphysics.co.uk/age16-19/Electronics/Logic%20gates/text/Logic_gates/index.html)

# 2. I like Logic

> i like logic and i like files, apparently, they have something in common, what should my next step be.

## Solution:

- i opened the .sal file in the logi2 software and then used the Async seriel analyzer on the channel 3 and it show the ascii text for the frequency graph and i found the flag among that text.

<img width="1518" height="743" alt="Screenshot 2025-10-31 222106" src="https://github.com/user-attachments/assets/cdc89117-7cdc-4077-b943-9c345c2a2491" />


## Flag:
```
FCSC{b1dee4eeadf6c4e60aeb142b0b486344e64b12b40d1046de95c89ba5e23a9925}
```

## Concepts learnt:

- I learned .sal files can be analzyed using the Logic2 software and Async seriel analyzer can be used to get the ascii text.

## Notes:

- i kept using othe analyzers such I2C,SPI and concatenator but they didn't work. 

## Resources:

-  (https://file.org/extension/sal)

