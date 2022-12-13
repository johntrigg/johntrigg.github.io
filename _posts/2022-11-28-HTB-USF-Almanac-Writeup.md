---
layout: post
category: writeups
---

Almanac is a binary reverse-engineering challenge that was hosted at HTB's CTF at USF during the fall 2022 semester. We are given a Linux ELF executable, and unsurprisingly, we are meant to extract a flag from it.

To begin, I imported the binary file into Ghidra. I found the main function, and inspected it.
!(https://github.com/johntrigg/johntrigg.github.io/blob/master/assets/images/writeups/almanac/almanac-writeup-screenshot-1.PNG?raw=true)

Let's take a look at what the program actually does. It takes some values from the user, and uses those to drive the program. One input is a year, the other is the type of sport.

Hmm, what an unusual check. If the local_14 variable corresponds to a value of 0x7169 in hex, it calls some unusual function. We know that local_14 corresponds to the first value that the program takes from the user (the year). 

So, Converting 0x7a69 from hex to decimal gives us the value. 
!(/assets/images/writeups/almanac/almanac-writeup-screenshot-1.PNG)

Let's plug it into the program (specifically as the local_14 variable), and see what that special functions does, exactly.
!(https://raw.githubusercontent.com/johntrigg/johntrigg.github.io/tree/master/assets/images/writeups/almanac/almanac-writeup-screenshot-3.PNG)

Well, there we are. That's a flag. Thanks for reading!