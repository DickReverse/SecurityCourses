In this one, we list some challenges related to memory forensics. 

# https://tryhackme.com/room/memoryforensics

Complete all tasks 
## Task2 - Login

Hint : check hashdump module.

## Task 3 - Analysis
Hint  : use volatility 2.0 and specific modules related to the console
EVTX could be useful there.

## Task 4 - TrueCrypt
Hint  : use volatility 2.0 and specific modules related to the console

# Pulling threads
Source : https://drive.google.com/drive/folders/1wDj2KjHhRHVJBc9dpK54Zy2uhGjOs73Y
Walkthrough : 13Cubed

## Identify Process with Connections
Some processes are associated with a connection.
Find them.

## Which port is "weird" ?

Obtain the IP address and port associated with this weird connection.

## Find the command that is related to the IP address 
List the command.

# MiniCTF - 13Cubed
**Source** : Youtube channel 13Cubed

https://drive.google.com/drive/folders/1E-i2RTUBXBGUd_Xz0k67kFOpHcr6WX8J
Solution : https://www.13cubed.com/downloads/mini_memory_ctf_solutions_guide.pdf

```
python2 volatility/vol.py -f /data/13Cubed/memdump.mem --profile=Win10x64_17134 pslist
```

## Question #1 Find the running rogue (malicious) process. 
The flag is the MD5 hash of its PID. 


## Question #2 Find the running rogue (malicious) process and dump its memory to disk. 
You'll find the 32-character flag within that process's memory. 
[[Volatility]]

## Question #3 What is the MAC address of this machine's default gateway? 
The flag is the MD5 hash of that MAC address in uppercase with dashes (-) as delimiters. Example: 01-00-A4-FB-AF-C2. 

## Question #4 Find the full path of the browser cache created when an analyst visited "www.13cubed.com." 
The path will begin with "Users\." Convert the path to uppercase. The flag is the MD5 hash of that string.

## MemLabs 
Link : https://github.com/stuxnet999/MemLabs

Do as many challenges from this lab as possible.

