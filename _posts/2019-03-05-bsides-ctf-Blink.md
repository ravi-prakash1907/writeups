---
layout: post
author: eshaan7
---

### Challenge: Blink(for 50 points)

	Description:
	
	Get past the Jedi mind trick to find the flag you are looking for.
	File: blink.apk

<br/>
On installing the app on a mobile, we see this:

<img src="https://raw.githubusercontent.com/Eshaan7/CTFs_datadumps_2019/master/BSidesSF_CTF_2019_WithWriteups/50_blink_COMPLETE/appMobileSS.png" width="250px" height="350px">

Then I used apktool to decompile it.

    apktool d blink.apk

Going into the smali folder created by apktool

    blink/smali/com/example/blink

There’s a `r2d2.smali` file. Inside there’s a string of base64 encoded image.

<img src="https://raw.githubusercontent.com/Eshaan7/CTFs_datadumps_2019/master/BSidesSF_CTF_2019_WithWriteups/50_blink_COMPLETE/r2d2img.png">

I saved the string to `blink_r2d2.txt`

    cat blink_r2d2.txt | base64 -d > flag.png

On decoding the base64 string, and we get an image and the flag.

<img src="https://raw.githubusercontent.com/Eshaan7/CTFs_datadumps_2019/master/BSidesSF_CTF_2019_WithWriteups/50_blink_COMPLETE/flag.jpg">

#### Thankyou for reading, happy hackin'! ~ [eshaan7](https://eshaan7.cf/)
