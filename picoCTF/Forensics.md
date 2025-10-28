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

# 2. tunn3l v1s10n

>We found this file. Recover the flag.

## Solution:

- i couldn't open the file initailly so i tried looking its bytes to know more about the file. I found that this file had the initial bytes of a .bmp file so one checking further i gound that its DIB bytes were not the usual ones so i changed it to the standard bytes (28 00 00 00) but this only got me a portion of the image which said it wasn't the flag. So i then tried playing around with its width and height and when i cahnged the height to (32 03 00 00 ) the flag was shown in the image.

- the original bytes of the bmp file

<img width="843" height="409" alt="Screenshot 2025-10-24 231148" src="https://github.com/user-attachments/assets/3417af1f-19cf-4c8d-9515-96ec047638d8" />


- the changed DIB bytes of the given file

<img width="1831" height="898" alt="Screenshot 2025-10-27 200938" src="https://github.com/user-attachments/assets/98061ee2-9716-4b84-a11b-120a6de22da2" />

- The image after this

<img width="1719" height="459" alt="image" src="https://github.com/user-attachments/assets/71692726-7d77-4f85-a262-b7e11eb33a72" />

- the changed height bytes of the bmp file:

<img width="1774" height="927" alt="Screenshot 2025-10-27 201414" src="https://github.com/user-attachments/assets/ef2cdd3b-caee-4f78-938c-5a937fb62c3a" />

- the final image:

<img width="1146" height="827" alt="image" src="https://github.com/user-attachments/assets/e742fd32-5f2b-4e84-afab-ece45d17524a" />


## Flag:

```
picoCTF{qu1t3_a_v13w_2020}
```

## Concepts learnt:

-  i learned how each byte of a bmp file is associated with one of its file attributes.

## Notes:

- I kept changing the bytes to wrong ones and was not getting to open the bmp file as only specific litte endian values could get the right image configuration.

## Resources:

-  (https://www.youtube.com/watch?v=kpHFFFu9qeU)


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

- I learned how SSTV software can be used to encrypt any image into an audio file using audio tones.

## Notes:

- i kept trying out different stegnagraphic tools might work to get the flag but none worked.I thought maybe this challenge had something to do with stegnagraphy but it wasn't.

## Resources:
- (https://vu2nsb.com/cw-digital-radio/slow-scan-tv-sstv/)

-  (https://www.reddit.com/r/wireshark/comments/6ndvpq/extract_tftp_file_from_pcapng/)
