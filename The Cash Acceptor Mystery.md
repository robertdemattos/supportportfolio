**The Cash Acceptor Issue**

**Situation**

Back when I worked on ATM machines (which I worked on for a decade) we had a brand new machine in a newly remodeled downtown branch that would stop accepting cash deposits.  Other techs had been out and had replaced the entire cash acceptor but the issue kept re occurring.  The customer was growing frustrated because this was the "show off" branch.  A flag ship of others to come.  First techs were just checking it for jams and rebooting the ATM PC.  Then they were replacing parts.  Nothing fixed the issue.

**Task**

I was considered one of the better techs in the area at the time and they asked me to have a look at it.  So the plan was to speak with all of the techs who worked on it about what they saw and also try to glean if there was a particular time this was occurring.  I also wanted to make sure that USB connections, hubs and control boards had also been checked.

**Action**

1. I spoke with the techs who worked on it and they were all flustered and flabbergasted by this machines behavior but they did give me a good point of reference.  The machine would stop accepting cash after 7 pm when it did break.
2. I found that odd but one thing that did spring up in my head was the ATM servicer.  The ATM servicer is generally there to load the machine with money, pull money accepted by the cash acceptor and also put a new role of receipt paper in if it is getting low.  I had the number of the coordinator for the armored service and asked him to tell me how often our problem machine got serviced.  It was at 7 pm and it matched up perfectly with the days the machine broke.  But...I wasn't ready to blame the ATM servicer.  I had to go take a look for myself.
3. I got down to the machine on the next report of the cash acceptor being offline and I noticed in the computer that the PC couldn't see it.  The device was USB run.  The USB external hub showed every device lit except for one.  So I knew that the device was losing communication with the PC....but WHY???.
4. Something to note before I continue.  Cash acceptors and cash dispensers have to be racked out to be serviced or replaced therefore the electrical and communication cabling harness has to be routed through a flex chain designed to keep everything in one place.  I went ahead and restarted the computer and the cash acceptor came back up.
5. Because I knew the servicer had to rack the unit in and out, I decided to test it.  I racked it out, ran it, racked it in, tried to run it but it had gone offline again.  So I knew what I had to look at. Something is wrong in the harness somewhere.
6. I racked the cash acceptor in and out observing the harness and what I noticed was that the harness was hitting the safe wall.  It's not insulated.  It's made of metal. Upon racking out the acceptor again I began to pull out just the USB cable from the harness.  That is when I found it.  Right at the part of where the chain stopped folding, was an exposed piece of wiring in the USB cable.  I knew what I had to do.
7. I ordered a new USB cable but I also ordered a new chain for the harness.  Generally when these came off the build floor, the harnesses were an assembly to include the communication cable and electrical already in the chain.  I wanted to put my own touch on putting the wiring back in the chain.  So I replaced the USB cable after removing the chain and letting the harness hang.
8. I then took my time and put the harness back in the chain very carefully making sure to put the USB cable into the center of the wiring harness as to be protected by the electrical wiring and the chain around it.
9. I then checked to make sure that the chain wasn't touching the safe wall.  Because I had done it by hand, the chain had the clearance it needed now.

**Result**

I rebooted the ATM and got the acceptor back right away. I then tested the acceptor racked in and out several times for a good forty minutes.  I also ran already processed cash through the unit.  Everything I did worked and then acceptor never quit.  I then informed the customer and the issue never returned.  The root of the issue was the short being triggered unknowingly by the servicer.  This wasn't their fault though.  They were operating the machine as they had been trained and the issue was created at or before installation of the ATM.  I wrote up a small document (field techs had limited resources) to do thorough checks on device harnesses and even replace harness chains that were broken at any point.  
