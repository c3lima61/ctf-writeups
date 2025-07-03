<div align="center">

# Nightmare Fuel Write-Up
:vibration_mode: :vibration_mode: :vibration_mode:

##### 03/07/2025

#### Contract and the ZIP file can be found [here](https://hacktoria.com/#easy).

Simple one if you have used metadata tools before.

</div>


***


### Noteable Materials

- Bodycam footage in MP4 format
- The encrypted ZIP file containing the badge
- Story PDF file

### Briefing Clues

- None really except for the flag format instruction.

### Flag format

A long string of different characters

***

### Steps

##### Step One:

Download and unzip the file:

`unzip nightmare-fuel.zip`

You will find the materials previously mentioned. Run:

`file flagfile-nightmare-fuel.zip` 

You'll see that it is encrypted with AES so you need to find the password, i.e. the flag.

##### Step Two:

Watch the video, nothing really jumps out. If you do a reverse image search for the video on [google](https://www.google.com/) it will lead you to a [getty images](https://www.gettyimages.co.jp/%E5%8B%95%E7%94%BB/ghost-hunting-equipment) page (sorry if it's in Japanese) that won't provide any help unless you want to know how much the footage cost.

##### Step Three:

Best place to start now is checking the metadata, i used [exiftool](https://exiftool.org/):

`exiftool bodycam-officer-1.mp4`

You'll see towards bottom of the metadata, in the *comment* value, there is a long string that matches the flag format.  

##### Step Four:

Unzip the encrypted flag file, enter the *comment* value into the password field and get your badge!

`7z x flagfile-nightmare-fuel.zip`

Thanks for reading.

c3lima61 :mobile_phone_off:

