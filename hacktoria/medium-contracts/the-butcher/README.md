<div align="center">

# The Butcher Write-Up
:vibration_mode: :vibration_mode: :vibration_mode:

##### 16/11/2026

#### Contract and the ZIP file can be found [here](https://hacktoria.com/#contracts).

A simple DFIR-style CTF involving a large hex dump that took me around 15 minutes to solve.

</div>


***


### Noteable Materials

- A ZIP file containing the hex dump
- The encrypted ZIP file containing the badge
- Story PDF file

### Briefing Clues

- "listen carefully"

### Flag format

Lowercase alphabetic string

***

### Steps

##### Step One:

Download and extract the ZIP file:

`unzip the-butcher.zip`

You will find the materials above. Run:

`file flagfile-the-butcher.zip` 

The ZIP archive uses AES encryption, so you'll need to find the password (the flag) before you can extract its contents.

##### Step Two:

Open the ` password-the-butcher` file that contains the hex dump. If you're familiar with common file signatures, you might recognise `49 44 33` as the [ID3](https://en.wikipedia.org/wiki/ID3) metadata signature, 
commonly found at the beginning of MP3 files. If you're unsure, paste the hex dump into [CyberChef](https://gchq.github.io/CyberChef/) and apply the *From Hex* operation. You'll notice readable strings such as ID3 and Lavf59.27.100. 
which identifies the version of the libavformat library used by FFmpeg.

##### Step Three:

Save the output to an MP3 file and download it.

##### Step Four:

Listen to the MP3 and write down what you hear. This is where the briefing clue helps.

##### Step Five:

Unzip the encrypted flag file, enter the string you heard into the password field and get your badge!

`7z x flagfile-the-butcher.zip`

Thanks for reading.

c3lima61 :mobile_phone_off:
