# Full Disk Encryption
<https://en.wikipedia.org/wiki/Disk_encryption>

## VeraCrypt
Open Source, works for any OS

## Security Concerns
#### Cold Boot Attack
First, the computers power is shut off during runtime. 
By aquiring physical access to a computer, a lightweight OS can be run from a device, and a memeory dump can be performed.
This is possible because of the properties of RAM, that data still remains readable to some extend for some period of time after the RAM lost power.
Keys stored in RAM or sensitive data can get exposed that way. 

#### Hibernate vs Suspend
Suspend doesn't turn off the computer, rather keeps it in low power consumption.
Hibernate saves state on hard disk and shuts down.
Afterwards the state is loaded into the RAM again.

Therefore stealing a computer in suspend mode won't require the BIOS boot sequence, i.e. the device would be decrypted.

#### Side Channel attacks
Unless the device uses self-encrpytion, i.e. implementation of FDE through hardware, there will be side channel attack opportunities.

#### Privacy vs Integrity
FDE doesn't protect from data corruption, i.e. it provides privacy but not integrity.
