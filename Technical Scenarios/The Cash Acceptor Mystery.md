# The Cash Acceptor Issue

---

## Situation

During my decade working on ATM machines, I encountered a recurring issue at a brand new ATM installed in a newly remodeled downtown branch — the flagship location for a series of branches to follow. The machine would intermittently stop accepting cash deposits. Multiple technicians had already been dispatched. The first wave checked for jams and rebooted the ATM PC. When that didn't work, the next wave began replacing parts including the entire cash acceptor unit. None of it resolved the issue. The customer was growing frustrated. This was their showpiece branch and it wasn't performing.

---

## Task

I was considered one of the stronger techs in the area at the time and was asked to take a fresh look. My approach was to start by talking to every tech who had worked on the machine to understand what they had seen and tried. I also wanted to find out whether there was a pattern — a specific time of day or circumstance when the failure occurred. Beyond that I wanted to confirm whether USB connections, hubs, and control boards had been thoroughly inspected, since prior work had focused heavily on the cash acceptor hardware itself.

---

## Action

1. I spoke with each of the techs who had worked on the machine. They were all genuinely stumped by its behavior, but they gave me one useful data point — when the machine did fail, it always happened after 7 pm.

2. That timing immediately made me think of the ATM servicer. The armored service team is responsible for loading the machine with cash, retrieving deposited funds from the cash acceptor, and replacing the receipt paper roll when it runs low. I contacted the coordinator for the armored service and asked how often our problem machine was being serviced. The answer was 7 pm — matching perfectly with the days the machine failed. But I wasn't ready to point the finger at the servicer. I needed to see it for myself.

3. On the next report of the cash acceptor going offline I went to the machine and pulled up the computer. The PC couldn't see the device at all. The cash acceptor was USB connected and when I checked the external USB hub every device showed as lit except for that one. The device was losing communication with the PC. The question was why.

4. Before going further it's important to understand how these machines are built. Cash acceptors and cash dispensers have to be racked out on a sliding mechanism to be serviced or replaced. Because of this the electrical and communication cabling runs through a flex chain — a protective assembly designed to keep the wiring organized and intact as the unit slides in and out. I restarted the computer and the cash acceptor came back online, which told me the connection wasn't permanently broken. Something was interrupting it.

5. Knowing that the servicer had to rack the unit in and out during every visit I decided to replicate that process. I racked the cash acceptor out, ran it, racked it back in, and tried to run it again. It went offline immediately. That told me exactly where to look. Something in the harness was the problem.

6. I racked the unit in and out slowly this time, watching the harness carefully. That's when I noticed it — the harness was making contact with the safe wall. The safe wall is not insulated. It's bare metal. I racked the acceptor out again and began carefully separating the USB cable from the rest of the harness. Right at the point where the flex chain stopped folding, I found it — an exposed section of wiring on the USB cable. Every time the servicer racked the unit in and out, that exposed wire was grounding against the metal wall and knocking the device offline. I knew exactly what needed to be done.

7. I ordered a new USB cable and a new flex chain for the harness. Typically these units came off the build floor with the communication and electrical cabling already assembled inside the chain as a single unit. I wanted to do this one differently — by hand, with intention. I replaced the USB cable first, removing the chain entirely and letting the harness hang free so I could work cleanly.

8. I then rebuilt the harness by hand, carefully routing the new USB cable through the center of the wiring bundle so it would be surrounded and protected by the electrical wiring on all sides, with the chain enclosing everything around it.

9. Once reassembled I verified that the chain had proper clearance from the safe wall. Because I had done it by hand rather than relying on the original factory assembly, I was able to position it with the clearance it needed.

---

## Result

I rebooted the ATM and the cash acceptor came back online immediately. I then racked the unit in and out repeatedly for about forty minutes, running already processed cash through it each time to stress test the repair under real conditions. Everything held. The acceptor never dropped.

I informed the customer and the issue never returned.

The root cause was a short circuit created by an exposed USB cable making contact with the uninsulated metal safe wall every time the unit was racked in and out during servicing. This was not the servicer's fault. They were operating the machine exactly as they had been trained. The fault lay in how the harness had been assembled at or before installation — with insufficient clearance from the safe wall and no protection around the USB cable itself.

After resolving the issue I wrote up a brief document for field techs recommending thorough inspection of device harnesses on all units and replacement of any flex chains showing wear or damage. Field techs had limited documentation resources at the time, but this was worth putting on paper.

---

*Robert de Mattos | robertdemattos@yahoo.com | linkedin.com/in/robert-de-mattos-16b8ab5*
