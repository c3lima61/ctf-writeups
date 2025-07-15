<div align="center">

# Naval Intrusion Write-Up
:vibration_mode: :vibration_mode: :vibration_mode:

##### 16/07/2025

#### Contract and the ZIP file can be found [here](https://hacktoria.com/#easy).

Easy would be an understatement for this one.

</div>


***


### Noteable Materials

- Ship png image
- The encrypted ZIP file containing the badge
- Story PDF file

### Briefing Clues

- An unidentified military vessel has been spotted near Taiwan. Given current geopolitical tensions, it is likely to be of Chinese origin.

### Flag format

type-123q-nato-reporting-name

***

### Steps

##### Step One:

Download and unzip the file:

`unzip naval-intrusion.zip`

You will find the materials previously mentioned. Run:

`file flagfile-nightmare-fuel.zip` 

You'll see that it is encrypted with AES so you need to find the password, i.e. the flag.

##### Step Two:

If you do a reverse image search on [google](https://www.google.com/) it will lead you to this [wikipedia](https://en.wikipedia.org/wiki/Type_054A_frigate) page. Let's try use the class as the flag.

##### Step Three:

Unzip the encrypted flag file:

`7z x flagfile-nightmare-fuel.zip`

Enter *type-054a-jiangkai-ii* into the password field — success! Grab your badge!

Thanks for reading.

c3lima61 :mobile_phone_off:
