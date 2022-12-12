EECSucka - a ROM dumper for the EEC-IV
--------------------------------------
Distribution file version 1.11, 16-Jan-99.

by 
Andrew March
amarch@icenet.com.au
www.icenet.com.au/~amarch


Disclaimer 
----------
This release of the EECSucka hardware plans and software is supplied without any warranty 
whatsoever, use at your own risk. I have built the unit and it works to my satisfaction. 
Your mileage may vary. 


Important
---------
EECSucka is presented for educational and archive purposes. What you do with your 
ROM dumps is your own business. I will not be providing ROM dumps so DON'T ASK.

This is a constructional project. There is no PCB in this release, you have to wire 
it by hand. See the photos to get an idea of what is involved. 


Terms
-----
EECSucka is presented as a freeware project for individual use on a non-profit basis. 
Copying and dissemination of the distribution file is encouraged and welcomed provided
its contents are not altered in any way. 

Commercial enquiries regarding purchase of PCBs, kits, built up units, customisation, 
licencing or retailing should be sent to amarch@icenet.com.au.   


Distribution file contents (eecsk111.zip)
-----------------------------------------
readme.txt       Yep, you're reading it.
eecsk200.pdf     Schematic of hardware version 2.00
eecsucka.exe     DOS software executable version 2.10
esk_top2.jpg     Top view photo of my prototype
esk_bot2.jpg     Photo of wiring side of my prototype
esk_eec2.jpg     Photo of the EECSucka connected to an EEC-IV 


Revision History
----------------
eecsk100.zip     First release 9-Nov-98
eecsk110.zip     Second release 16-Jan-99
                 Added esk_eec2.jpg, added terms and acknowledgements to readme.txt.        
eecsk111.zip     Third release 16-Jan-99
                 Added description of EEC-IV ROM operation.


What is the EECSucka?
---------------------
The EECSucka allows a PC to read the contents of the ROM inside an EEC-IV engine 
control unit used in many Ford automobiles and light trucks. 

The EEC-IV ROM is a strange beast, not at all like the usual 27C256. Although both 
types of ROM hold 32K bytes, the similarity stops there. The EEC-IV ROM communicates 
with its MCU over a proprietary multiplexed bus known as MBUS that squeezes all 
address, data and control lines onto just 11 pins. The ROM contains an internal 
16-bit address counter which saves the MCU the effort of sending sequential addresses 
during non-branching code execution. 

The EECSUCKA clocks the address counter by strobing an auxiliary test input pin. As 
the address counter is 16 bits wide it can access up to 64K bytes, although the 
memory beyond the first 32K bytes contains the blank value of $FF. Clocking past 
$FFFF causes the counter to rollover to $0000. 

The unit plugs into the J3 service port at the rear of the EEC-IV and receives
its operating power from the EEC-IV itself. The EEC-IV must be operating from a +12V 
supply during ROM dumping. ROM dumping can be done in-vehicle if desired, but with the 
engine STOPPED.


How do I use the software?
--------------------------
The software runs under DOS or in a DOS box under Windows. Copy the executable
eecsucka.exe to your working directory and at the DOS prompt type
  eecsucka -h 
to see a full list of available commands.

 
Constructor's notes:
--------------------
The pin numbering of J1 reflects the use of an IDC header. This numbering is 
NOT the same as a DB25. The relationship to a DB25 is as follows:

J1-1    DB25-1
J1-2    DB25-14
J1-3    DB25-2
J1-4    DB25-15
J1-5    DB25-3
J1-6    DB25-16
J1-7    DB25-4
J1-8    DB25-17
J1-9    DB25-5
J1-10   DB25-18
J1-11   DB25-6 
J1-12   DB25-19
J1-13   DB25-7 
J1-14   DB25-20
J1-15   DB25-8 
J1-16   DB25-21
J1-17   DB25-9
J1-18   DB25-22
J1-19   DB25-10
J1-20   DB25-23
J1-21   DB25-11
J1-22   DB25-24
J1-23   DB25-12
J1-24   DB25-25
J1-25   DB25-13
J1-26   no connection

The J3 service port connector was made by soldering a right angle dual row 
0.1" header to a double-sided edge connector salvaged from a floppy disk 
drive cable. The crimped-on ribbon cable was peeled away to reveal the IDC 
knife edge contacts prior to soldering on the right-angle header.


Acknowledgements
----------------
The EECSucka was inspired by members of the EEC mailing list 
(http://eelink.umich.edu/~p-nowak/eec-efi/EEC-Mailadddrop.html)who have banded together 
with the common aim of understanding the inner workings of the ECUs in their beloved Ford 
motor vehicles. 

Special mention must go to Tom Cloud (cloud@peaches.ph.utexas.edu) for diligently 
compiling many individual contributions into the EEC-IV Technical Notes document, 
and Emmett Stanicki (estanick@iaw.com) for technical advice regarding the J3 port.
 

Happy dumping!

