---
title: Satori Frequently Asked Questions
author: Jonah Silas Sheridan
date: 11/11/2015
---    

#Satori Reference
##FAQ

**How can I verify files using sha256 checksums?**  
A checksum is number that acts a unique fingerprint of a file or program. Using this number you can verify that a file you are going to use is the same one you saved, received or downloaded. 

In Satori you can navigate to the "Verify" section, click "Select File" and choose any file for which you want to create a unique fingerprint. Satori will show you the sha256 checksum (which is a lot of letters and numbers) and wo;; tell you if there is a specific program (both the name and the version) that matches that fingerprint. 

If you generate the sha256 checksum for some file or program other than software you downloaded through Satori you can store it in a file or on paper. Later when you want to access that same file or program you can repeat the process and make sure the checksums match. This certifies that the file you accessed the second time is the same as the one you had the first time.

Similarly when sharing a file or program with someone else you can give them the sha256 checksum that you generated in Satori so they can confirm that the file or program they received is the same one you wanted to share. 

This last case is how Satori functions, generally. The software developers that make the tools that are available through Satori publish the checksum of each version. When you use the "Verify" section to get the checksum of something you downloaded, Satori checks to make sure the file you have is the same one the software developers created and shows you a green checkmark and the name and version of the software, assuring you that the program you downloaded was not altered on its way to you.

**How can I verify file using GPG?**  
Once you have installed GPG software on your computer, you can use it to certify that the source of a file or program is who you think it is. To do this, however, the file either needs to have an "inline signature" or a "detached signature" provided by whoever produced it and you need to also obtain the public GPG key of the signature producer as well. Many software developers supply both signature files and public keys on their websites.

"Inline signatures" are commonly only used for text files and emails while detached signatures can be used for any file including software you download. An inline signature means your file will end with a block of text that is in the form:

-----BEGIN PGP SIGNATURE-----

owF9WWuMJNV1Xgx+MNEqQATYwU6Kh2Gm6e1l17y8C7H3wcIazA47m10sKya3q253
l6e6bnNv1cw0Way1QAGHtYwTRxYCDFhJkI2DDbFJZMdGhkQWsDZSBCIgIoUVCgH8
f240T197/oufa3/p2dfObj1+y63Pt7ZfvWHxJyeaO24+665L3j7rifEf33D5P//h
Kbed+tRb7eLbr8cXxvvigxd/6eB1dx33+t9t2mXvvO/QD/auW3vMh/4f
=ke6H

-----END PGP SIGNATURE----- 

The long string of numbers, letters and symbols is the important information and may be very long. A "detached signature" is the same as this block of text except it is stored in a separate file from the program or document you wish to verify. Usually this separate file will have the same name as the original file but with .pgp or .asc added on. So the detached signature for file.txt will be called file.txt.gpg or file.txt.asc. If tje signature file ends in .gpg you probably cannot read the file in a word processor or text editor. If is ends in .asc you should be able to read the signature in a text editor or word processor.

To actually verify the GPG signature, whether "inline" or "detached" you need to also obtain the public GPG key of the person or people who created the signature. Again many software developers provide this information on their websites and elsewhere, but you also may need to contact them to download. 

Nearly any of the GPG tools available through Satori will allow you to check a GPG signature once you have all this information but each one is different so we refer you to the specific tool's manual or documentation for reference on actually performing the verification.

Adding GPG signature verification feature is on the roadmap for the next version of Satori.

**What are Tor bridges for and how do I use them?**  
A Bridge Relay is a server in the Tor network that is not publicly announced and so harder to block. If you choose to use a bridge, the server can provide you with access to the Tor network even if Tor is blocked in your country or network. Bridge relays are specified as an "ip address" (four numbers separated by periods) followed by a colon and another number called the "port number." You enter these in your Tor software to use that bridge. Bridges may also use Pluggable Transports which help hide your Tor activity, making it harder to block.

**Where can I get more bridge addresses?**  
There are a number of ways to get more Tor bridge addresses including leaving the Bridges section in Satori and returning to this section.

Additionally you can visit https://bridges.torproject.org for a fresh list of bridges.

The Tor Project also provides an Email Autoresponder to supply bridge information. To use that service, send an email from a riseup.net, gmail or yahoo.com address to bridges@torproject.org with only the words "get bridges" in the body of the message. You will receive an email back with multiple new bridge addresses. 

As a last resort you can contact the Tor Project help desk by sending a polite email request to help@rt.torproject.org. Please note that a person will need to respond to that request so it may take some time. 

If you are considering using the help desk, you may wish to read the answer to "Why don't any bridges work for me?" in this FAQ.

**Why don't any bridges work for me?**  
If you are consistently unable to connect to the Tor network even using the bridge addresses you get from Satori, it is likely that that your Internet Service Provider (ISP), government or some other group is blocking more than just specific addresses using Deep Packet Inspection. In this case you will also need to disguise your Tor traffic as something that isn't blocked where you are to access the Tor network. Tor offers a system of Pluggable Transports that will help you do this. See "What are Pluggable Transports?" and "How do I use Pluggable Transports?" in this FAQ.

**What are Pluggable Transports?**  
Pluggable Transports are small pieces of software that can be added to Tor software to make your connection to the Tor network through a bridge look like something else that is harder or impossible to monitor and block. There have been a whole range of these created that make your connection look like everything from online games to web searches. Pluggable transports are the best way to connect to Tor when on a network filtered or blocked using Deep Packet Inspection. These connections have to happen through specific bridge relays that have been configured to use them. This is why sometimes you will see a small word, "obfs3" or "scramblesuit" for example, in front of a bridge address you have received. That word is telling you what kind of Pluggable Transport that bridge can use which will enter into the settings of your Tor based tool.


**How do I use Pluggable Transports?**  
Pluggable Transports are entered into the settings for your Tor specific tools such as Tor Browser Bundle. They are often delivered to you as a small word in front of a bridge relay definition. In your Tor software you can specify the Pluggable Transport type when you enter your bridge information by leaving that word in place. Tor Browser Bundle also lets you specify a type of Pluggable Transport to use, which it will use with its already known bridge addresses rather than one you provide. This second way of using Pluggable Transports will not get you around networks where access to the Tor network is blocked.
 