# The War Room

Urgent issues will always be the bane of a support team's existence. When something affects a handful of customers or all of them at once, every other open issue becomes secondary until the fire is out.

It is worth understanding the difference between a customer's perception of an urgent issue and an actual urgent issue. A customer may consider a how-to question urgent. But if the service needed to answer that question is down and the customer cannot use the product they are paying for, that is an actual urgent issue. One requires guidance. The other requires mobilization.

---

## What Is a War Room?

Not every company calls it a War Room and not every company handles urgent issues this way. But the concept is the same regardless of what it's called. A War Room brings together all of the key players immediately when an urgent issue affects a significant portion of a product's customers or all of them at once. When a customer's business and bottom line are impacted by an outage, a slow response from the support team puts the provider's bottom line at risk too. Customer Success professionals call this churn. Churn means customers leave to spend their money on a product they believe is more reliable. A well run War Room is one of the most effective ways to prevent that from happening.

By my experience the most effective War Room runs through Slack. When a service goes down a dedicated channel is created, the right people are brought in immediately, and communication flows in real time rather than through a chain of delayed messages and missed context.

---

## A Cloud Service Outage: How It Unfolds

Most SaaS applications run on cloud services today because they are web based. No installation required. The customer opens a browser and they are in. So what happens when the service goes down and it is managed by your company? Here is how that scenario typically unfolds from first report to resolution.

1. A support agent gets a phone call. The customer cannot access the web based product. The agent assumes it is a singular issue. Then another agent gets the same call.
2. By the fourth report, with agents attempting to pull up the customer's site themselves, a common theme emerges. The cause is not yet known.
3. A general discussion opens in the support Slack channel. The team begins checking basics — services running within the cloud based virtual server, tools within the cloud platform like AWS that keep the application running under load. Everything appears normal on the surface. Even the cloud service status check comes back clean.
4. The Team Lead and Support Manager have been reading the discussion and the notes. Fifteen minutes have passed since the first report. They determine this is an outage.
5. The Team Lead creates a War Room channel in Slack. It is titled with the ticket number, a brief description of the issue, and the affected customer or customer base. The support team, Customer Success, Engineering, DevOps, and C-level leadership are all invited in.
6. Support and Engineering begin communicating in the War Room on what has been investigated so far.
7. Customer Success and C-level begin working out, in a separate thread, how to handle damage control and what to communicate to customers while the investigation is active.
8. DevOps reviews the notes shared by Support and lets the War Room know they have started a deep check of systems.
9. Support receives directives from management in their own channel on how to communicate the outage to customers calling in and how to manage the volume of incoming tickets.
10. DevOps finds that two services within the cloud platform are not communicating with each other and shares that update in the War Room. Everyone knows in real time that the team is closer to a fix.
11. DevOps provides an updated ETA in the War Room channel.
12. Support communicates the updated ETA to customers. Customer Success is aware in case customers reach out to them directly.
13. DevOps resolves the issue and posts what the cause was and what the fix was.
14. Support communicates the resolution to customers and asks them to test.
15. Engineering and DevOps document the cause and the solution for future reference.
16. Customer Success prepares a resolution email to go out to the affected customer base.
17. C-level leadership has a full rundown ready in case contacts at higher levels of the customer organization reach out directly to express frustration.
18. Support builds or updates a process document to investigate this type of issue faster if it surfaces again.
19. A monitoring period begins with the War Room channel kept active for a week or two.
20. Once the monitoring period is complete and the issue has not returned, the War Room channel is archived or deleted.

---

## What the War Room Prevented

Without a War Room, communication in a remote environment quickly becomes a game of telephone. Information gets delayed, the wrong people learn about the issue too late, and by the time a fix is in motion customers have already lost confidence in the team's ability to respond. That loss of confidence leads to churn. Churn leads to lost revenue. And one major customer loss can force a company into decisions it was not prepared to make.

The War Room prevents all of that. But it only works when everyone in it responds quickly, knows their role, and acts with accountability and urgency. When those conditions are met it is one of the most effective things a support organization can do. It is the best way to watch a fire get put out the right way.

---

*Robert de Mattos | robertdemattos@yahoo.com | linkedin.com/in/robert-de-mattos-16b8ab5 | github.com/robertdemattos/supportportfolio*
