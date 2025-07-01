<div align="center">

# Cold War Enemies Write-Up
:vibration_mode: :vibration_mode: :vibration_mode:

##### 01/07/2025

#### Contract and the ZIP file can be found [here](https://hacktoria.com/#easy).

A pretty simple CTF that took no longer than a couple of minutes to get the flag. I will not cover the story, but I recommend having a read if you have the time. 

</div>


***


### Noteable Materials

- A JPG satellite image of an airfield
- The encrypted ZIP file containing the badge
- Story PDF file

### Briefing Clues

- Russian airbase not located in Russia

### Flag format

country-governate-district-airbasename-air-base

***

### Steps

##### Step One:

Download and unzip the file:

`unzip cold-war-enemies.zip`

You will find the materials previously mentioned. Run:

`file flagfile-cold-war-enemies.zip` 

You'll see that it is encrypted with AES so you need to find the password, i.e. the flag. Analyze the satellite image of the airfield.

##### Step Two:

Pretty simple, open up your favourite search engine (i used [DuckDuckGo](https://duckduckgo.com/)) and search for *russian military bases abroad*. The first result should be a Wikipedia page titled [List of Russian military bases abroad](https://en.wikipedia.org/wiki/List_of_Russian_military_bases_abroad). 

On this page, you will see a list of current bases. You can go through each base that has an airfield, but to save you time: if you hover over [Khmeimim Air Base](https://en.wikipedia.org/wiki/Khmeimim_Air_Base), you'll see that it matches the satellite image. 

From that page you'll now be able to substitute the correct names into the flag format, **syria-latakia-jableh-khmeimim-air-base**.

##### Step Three:

Unzip the encrypted flag file and get your badge!

`7z x flagfile-cold-war-enemies.zip`

Thanks for reading.

c3lima61 :mobile_phone_off:
