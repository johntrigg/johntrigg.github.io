---
layout: post
category: writeups
---

My team, Protosec, had the pleasure of attending HackSpaceCon this weekend. It was a crazy busy weekend for us, we secured high placing in a variety of CTFs (1st in USF HackTheBox CTF, 2nd and 3rd in Dark Wolf CTF, 1st and 2nd in Periwinkle CTF, and 4th in MetaCTF). I'd like to thank the organizers of these CTFs for making this even possible, and for making this weekend a lot of fun.

I think the most interesting challenge that I did over these past few days was one of the MetaCTF challenges, Telephony. 

The objective was to place a long-range call for free, to a certain number, that would give you the flag. However, since it was a long-range call, it would not go through for free (and you simply couldn't just pay for it).

The MetaCTF desk provided a flyer to help get started with the challenge.

After some research, we learn that Blue Boxes were used to place free phone calls. The way these worked was by playing tones of a certain frequency into a telephone reciever. These tones corresponded to commands, and certain numbers. When you dial a phone number, you hear certain tones. MetaCTF provided a blue box on their website.

IE, playing frequency A into the reciever is functionally equivalent to pressing the number X. This is a constant relationship that doesn't change. Additionally, there are certain commands that correspond to certain frequencies. Playing a 2600Hz tone, for example, puts the phone into stand-by mode to recieve commands.

Now, we have our problem statement: We use the phreak exploit (via the provided blue box) to "take over" the teleboard switch, so we can place the call we want.

My exploit chain was this:

Play 2600hz tone (Seize the trunk, so we can use the command frequencies), play a KP (key pulse, used to indicate the beginning of placing a number), play the corresponding frequencies of the last 4 digits of the target phone number, and play the ST (stop) tone to indicate we are finished.

This works after a try or two, and we obtain the flag.