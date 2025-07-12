<div align="center">

# CISCO - Salted Password
:vibration_mode: :vibration_mode: :vibration_mode:

##### 12/07/2025

#### Challenge can be found [here](https://www.root-me.org/en/Challenges/Cryptanalysis/CISCO-Salted-Password).

Couldn't find a write-up for this challenge, so I thought I'd write one. It's a pretty easy challenge, but it does require some hashing and Cisco Systems knowledge. 

</div>


***


Head to the challenge page, download the text file and read the contents using `cat -A ch53.txt`. We get a legacy Cisco router config:

<pre>
{!$
version 15.1$
no service timestamps log datetime msec$
no service timestamps debug datetime msec$
no service password-encryption$
!$
hostname R1$
!$
enable secret 5 $1$mERr$A419.HL58lq743wXS4kSM1$
!$
ip cef$
no ipv6 cef$
!$
username administrator secret 5 $1$mERr$yhf7f2RnC74CxKANvoekD.$
!$
license udi pid CISCO2911/K9 sn FTX1524V4VG-$
!$
no ip domain-lookup$
!$
spanning-tree mode pvst$
!$
interface GigabitEthernet0/0$
 ip address 10.0.0.254 255.255.255.0$
 no ip proxy-arp$
 duplex auto$
 speed auto$
!$
interface GigabitEthernet0/1$
 ip address 11.0.0.1 255.255.255.252$
 no ip proxy-arp$
 duplex auto$
 speed auto$
!$
interface GigabitEthernet0/2$
 no ip address$
 duplex auto$
 speed auto$
 shutdown$
!$
interface Vlan1$
 no ip address$
 shutdown$
!$
router bgp 1$
 bgp router-id 1.1.1.1$
 bgp log-neighbor-changes$
 no synchronization$
 neighbor 11.0.0.2 remote-as 2$
 network 10.0.0.0 mask 255.255.255.0$
!$
ip classless$
!$
ip flow-export version 9$
!$
no cdp run$
!$
line con 0$
 login local$
!$
line aux 0$
!$
line vty 0 4$
 login$
!$
!$
!$
}$
</pre>

It contains the privilege EXEC mode salted hash:

`$1$mERr$A419.HL58lq743wXS4kSM1`

And the administrator password hash:

`$1$mERr$yhf7f2RnC74CxKANvoekD.`

If you are familiar with Cisco routers or switches you will know `secret 5` indicates Cisco's MD5 password hashing format which is compatible with standard md5crypt hashes, a very weak hashing method by today's standards. If you are not familiar with Cisco systems you can use [haiti](https://github.com/noraj/haiti) or `ctrl + g` search the hashes [here](https://hashcat.net/wiki/doku.php?id=example_hashes).

Copy and paste both hashes into a text file and get cracking. You can use John or Hashcat, I will use Hashcat in this example:

`hashcat -m 500 -a 0 -o ciscocracked.txt --status --status-timer=30 ciscohashes.txt /usr/share/wordlists/rockyou.txt`

Took about 7 minutes for me but the cracked hashes can be found in the ciscocracked.txt file:

`$1$mERr$A419.HL58lq743wXS4kSM1:dolphinsforever`

`$1$mERr$yhf7f2RnC74CxKANvoekD.:P@ssw0rd!1`

Submit it in the correct format and get your points.

Thanks for reading.

c3lima61 :mobile_phone_off:


