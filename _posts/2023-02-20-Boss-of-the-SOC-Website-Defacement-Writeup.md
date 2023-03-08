---
layout: post
category: writeups
---


```Question 1: "What is the likely IPv4 address of someone from the Po1s0n1vy group scanning imreallynotbatman.com for web application vulnerabilities?"```

To begin, we start with a query of our website, to see if we can get a starting point.

![Boss Writeup Screenshot 1](/assets/images/writeups/boss/boss-screenshot-1.PNG)

After some scrolling, we see a very interesting request. It is from an external public IP (40.80.148.42) to our internal private IP(192.168.250.70). This in and of itself isn't very interesting - web servers are supposed to handle outside traffic.

However, we see something that should arise suspicion. The user agent is "Acunetix Web Vulnerability Scanner". This is highly abnormal. Since we didn't authorize this vulnerability scan, we can be fairly confident that this is the threat actor's IPv4 address (40.80.148.42).

```Question 2: "What company created the web vulnerability scanner used by Po1s0n1vy (the threat actor)?"```

The answer to this is in our previous screenshot. The threat actor used a vulnerability scanner created by Acunetix.

```Question 3: "What content management system is imreallynotbatman.com likely using?"```

This too, is in the previous screenshot. We see the name "Joomla" when file paths are references. A quick search reveals Joomla to be a CMS (content management system).

```Question 4: "What is the name of the file that defaced the imreallynotbatman.com website? Please submit only the name of the file with extension?"```



So, how do we figure this out? The website would be updated via the internal IP, and we can filter requests by the URL accessed. So, we want a query that checks what requests were made with a client ip (c_ip) of our web server, and look at the URL statistics. 

![Boss Writeup Screenshot 2](/assets/images/writeups/boss/boss-screenshot-2.PNG)

Most of the files don't arouse suspicion. However, that jpeg with an unusual name arouses some suspision, and is our answer.

```Question 5: This attack used dynamic DNS to resolve to the malicious IP. What fully qualified domain name (FQDN) is associated with this attack?```

This is in the above screenshot. We see a very unusual website where the image was hosted - "prankglassinebracket.jumpingcrab.com"