---
layout: post
category: writeups
---

The B-Sides Tampa 2023 CTF (one of them, anyways) was hosted by the Neon Temple. This was a very unique CTF, in context of the type of challenges that were given. Rather than traditional CTF challenge categories like cryptography, reverse engineering, and web exploitation, the categories of challenges were rather special, and focused on rather unique categories.

The categories were broken into the following areas:

Treasure Hunt (Critical Thinking and digital OSINT)

Pirate Hunting (Critical Thinking, forensics, and physical OSINT)

Piracy (Attack and Defend)

Sea Shanties (Musical Theory)

The flag format was also relatively unique: {NT-FLAG-TEXT-NT}.

# Treasure Hunt

## Up To No Good

The clue for this challenge was that we had to find a guy in a hat, who was the bane of a pirate lord, asked a question in every Neon Temple stream, and ask him about his favorite type of Pizza.

I had to let my pride down for this one, and asked everyone in a Neon Temple hat the question. My first choice (the fedora man) was actually the correct one, and the flag was MOSI.

{NT-MOSI-NT}


## Don't Forget to Subscribe!

This asks us for the scale of the song played in the 2023 B-Sides Tampa X Promotional video. I originally missed the word "scale" in this sentence, and got it wrong quite a few times.

I knew enough musical theory to get us through some of the challenges, but my musical ear was not nearly good enough to recognize key signatures (I played the Viola in middle school, and some guitar in high school). I did however know my key signatures. So, I figured I'd throw in some reasonable guesses.

After a few guesses (starting with what I remembered to be the most common), I got lucky. Thank god all C-Major is the most commonly used key signature, at least in most music.

{NT-C-MAJOR-NT}



## Tampa Dot Net

The goal here is to find the address of the Chick Fil A closest to the B-Sides Tampa website's domain registrar.

Shoutout to my teammate Jack W for getting this.

Running a quick `whois` on the B-Sides Tampa website revealed that the domain registrar was something like launchpad hostgator. Then, we looked for the address of HostGator HQ.

Then, we plug that address into google maps as "current location", and set our destination to be Chick Fil A. This should get us the address of the closest Chick Fil A, and it does. Formatting the flag was somewhat tricky, and took  a few tries.

{NT-11011-NORTHWEST-FWY-HOUSTON-TX-77092-NT}
## Schedule Your Manifest

This flag wanted to know the package name of the Android App for viewing information about the B-Sides Conference.

The app was Zoho Backstage. We can grab the package name by visiting the url of the Google Play Store page for the app.

https://play.google.com/store/apps/details?id=com.zoho.backstage

We can see the id, and therefore we see the pckage name. The flag is {NT-COM.ZOHO.BACKSTAGE-NT}

## 日々は一瞬が時間になったようなもの 

This questioned boiled down to "what performer and composer for the music of the show Cowboy Bebop wore a safety harness?"

The band that performed most of the music for Cowboy Bebop was 'The Seatbelts', and the composer was Yoko Kanno, so the flag was '{NT-YOKO-KANNO-NT}

## La Cumba

This asks for the CIP code for South University's Undergrad in IT. This one filtered me for awhile, since I assumed it meant "University of South Florida". After taking a break, I realized my error, and googled "South University Tampa undergraduate CIP codes", and quickly got the flag.


# Sea Shanties

## Fun Riddle Time #1

We are given a piece of a sheet music, with the prompt "Use the attached music to find the flag".

I was the only one on my team with any sort of musical background, and overlooked the simple answer. It was my teammate Jack (the other one) who asked me if the notes could be transcribed. I said yes, and when I transcribed the notes with him, the notes themselves were the answer, spelling out the flag.

{NT-GAGGED-NT}

## Sea Shanty #2

This one was tricky. We're given sheet music, and told to find the consumer. I hummed the tune, and my teammate put it into Musescore, but no luck. This one eluded us for a little while, until my teammate had the idea to write the notes down, and search for them.

We found this led to a piano tutorial for the song "He's a Pirate" by Hanz Zimmer. I initially doubted this, because the sheet music used quarter notes, and the melody for "He's a Pirate" has some sections that use eighth notes. However, it did end up being that song, and the flag was one of the composers.

## Sea Shanty #3

The challenge is to find out "What do we do with him?", accompanied by a sheet music. I immediately recognize the song after humming the notes, and get further validation by the challenge description. The song is "Drunken Sailor?". There were apparently multiple possible flags for this (since there are several verses on what is done with a drunken sailor), but I believe the one we submitted was {NT-SHAVE-HIS-BELLY-WITH-A-RUSTY-RAZOR-NT}, since it's the simplest of the verses that could potentially have been an answer (in my opinion).

## Hummed Shanties

For this challenge, we were given an audio file of a man humming a song.

I immediately recognized it as the TikTok song "Billy o Tea", which was actually called "Wellerman". It's a song about hunting whales. The flag was what event/story the song was based off of.

After some research, we find that a possible inspiration was the famous whale hunt "Moby Dick". After 6 of our 10 guesses, we found the flag. {NT-MOBY-DICK-NT}

# Piracy

## Naval Combat on the High Seas: Assemble the Fleets!

We simply got this flag for participating in the attack/dfend.

# Pirate Hunting

## In The Trench

As with all steg challenges, this is really throwing your head against the wall and going throw a list of tools until you either have the answer, or need to find more tools.

And as with all steg challenges, the tool you use last is always, without fault, the tool that is the solution. In this case, the flag is hidden in the exif data, so exiftools will yield us the flag.

## Hex Scanners

We are given some hex characters, and asked what premium security scanner Chris Kubecka utilizes. By throwing the hex characters into cyberchef, we are greeted with the answer.

{NT-CENSYS-NT}