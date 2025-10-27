# 1. trivial flag transfer protocol

>Figure out how they moved the flag.

## Solution:

- i opened the tftp file in the wireshark and observed that there were few files like instructions.txt, plan ,program.deb, and some pictures sent. i tried out different export features to get these files and export tftp object option worked. i found shifted cipher in the instructionbs and plan files. i decoded it usinfg ROT13 in cyberchef. These clues suggested that pictures had some encrypted info so i used an online stegnographic decoder to get that info. I tried out with each of the three images with different passwords but later i tried DUEDILIGENCE as hinted in the plan file and it worked for the third picture and I got the flag.

the tftp file in the wireshark

<img width="1918" height="1016" alt="image" src="https://github.com/user-attachments/assets/0a708d84-333c-48f4-8279-0ff432113ab8" />


the decoded text from instructions.txt file

<img width="1919" height="886" alt="image" src="https://github.com/user-attachments/assets/f82c49a7-944e-49b9-b112-70e544db9dbf" />


the decoded text from plan file

<img width="1749" height="691" alt="image" src="https://github.com/user-attachments/assets/75f06a97-0fa4-4cc9-b3c0-6f6727a2ed06" />


The online stegnographic decoder

<img width="1755" height="605" alt="Screenshot 2025-10-24 224438" src="https://github.com/user-attachments/assets/fe85e4de-6b49-4737-973c-fe77f314e9d6" />


the flag obtained by the decoder

<img width="459" height="300" alt="image" src="https://github.com/user-attachments/assets/438d58b1-b34a-429c-bffb-8d7ab3d701f9" />


## Flag:

```
picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_1fb380}
```

## Concepts learnt:

- I learned how tftp works to send data and how we extract files sent using this tftp in wireshark and also found how to use steghide to get encrypted info from images. 

## Notes:

- i kept trying out different option which were shown for each log in the wireshark when u right clicked and thought something might work to get the file but none worked.

## Resources:

-  (https://www.reddit.com/r/wireshark/comments/6ndvpq/extract_tftp_file_from_pcapng/)

# 3. m00nwalk

> Decode this message from the moon.

## Solution:

- i opened to find the audio .wav file with some sort of encrypted audio so tried using some stegnographic tools at first but it didn't work then i looked  at the hints provided so thorough those hints i found that this had to solve using the SSTV software. So iran this .wav file through a SSTV decoder to get the flag

The flag obtained by the SSTV decoder

<img width="1719" height="937" alt="image" src="https://github.com/user-attachments/assets/59d3a944-1204-4d37-8215-5a732cb33383" />


## Flag:

```
picoCTF{beep_boop_im_in_space}
```

## Concepts learnt:

- I learned how tftp works to send data and how we extract files sent using this tftp in wireshark and also found how to use steghide to get encrypted info from images. 

## Notes:

- i kept trying out different option which were shown for each log in the wireshark when u right clicked and thought something might work to get the file but none worked.

## Resources:

-  (https://www.reddit.com/r/wireshark/comments/6ndvpq/extract_tftp_file_from_pcapng/)
