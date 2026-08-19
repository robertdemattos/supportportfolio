# The AR Statement Issue

---

## Situation

A hospital accounts receivable employee responsible for pharmacy billing contacted support unable to print the 8,000+ patient statements he knew had outstanding balances. It was end of month. Statements needed to go out so patients could pay their bills on time. Instead of the 8,000+ statements he expected, only around 600 were showing as printable. Something was wrong and the clock was ticking.

---

## Task

My job was to find out why the application was only surfacing 600 statements when the data clearly showed far more accounts with balances. That meant starting at two places simultaneously — the database and the application itself — to understand where the disconnect was happening.

---

## Action

1. The first thing I checked was whether Hangfire, the cloud based application that replaced Windows Scheduler for batch processing, had properly triggered the AR batch preparation. I pulled the application log and confirmed it had fired approximately 15 minutes after the customer initiated the print action, which was normal behavior based on how the trigger was configured.

2. Next I went directly into the customer database and ran a SQL query to verify the accounts were actually there.

   ```sql
   SELECT * FROM tbltgarstatements WHERE accountbalance > 0
   ```

   More than 8,000 accounts pulled back. The data was in the database and it was correct. The problem was not missing data.

3. To make sure I was seeing what the customer was seeing and that the process was being followed correctly, I accessed the customer environment through our established access point and triggered an AR statement reversal to the previous month — essentially an undo on the batch run. I then triggered the AR print statement action the same way the customer had. Only around 600 statements prepped in the batch. I had recreated the issue and confirmed it was real.

4. I documented everything in Zendesk — my steps, findings, and screenshots — and brought it to engineering. As Team Lead and the Level 3 resource on the case it was my responsibility to bridge the support and engineering teams. I opened an Azure Boards ticket, updated the customer on where the investigation stood, and presented my findings at the engineering meeting the following day.

   The first question engineering asked was what version of the web application the customer was running. I had it. As they reviewed the version history they found that just prior to the customer reporting the issue the application had been updated to a new patched version that addressed several AR related problems. The question then became whether the SQL stored procedure had been updated alongside the patch. It had not. The stored procedure in the customer's environment was still written for the previous version. It had slipped through during the release process. Engineering connected me with the DBA responsible for writing and maintaining stored procedures for each application version.

5. I worked with the customer to explain that our DBA, who had no direct database access, would need to get in to examine the stored procedure and compare it against the patch notes to understand what needed to change. The customer agreed and authorized me to facilitate access through my own credentials.

6. With coordinated access established the DBA pulled the stored procedure, brought it into a test environment, and began working through what the newest version of the application required. Once he was satisfied with his test results I gave him access and he deployed the updated stored procedure. We triggered the AR run. 2,000 statements. A meaningful improvement but still well short of the mark. I kept the customer informed throughout.

7. The DBA went back in, made further adjustments, redeployed, reversed the batch, and ran it again. 5,000 statements. Closer, but not there yet.

8. At that point the DBA told me he needed a couple of days and wanted to work more directly with the end user to understand exactly what the output needed to look like. I asked him whether he wanted me present as an intermediary or whether he felt comfortable engaging the customer directly since he didn't typically work customer facing. He said he was comfortable going directly and I trusted his judgment.

9. A couple of days later he had made his final adjustments but asked me to be present when the end user ran the test. I was there.

---

## Result

Because the customer had been communicated with consistently throughout — first by me and then jointly with the DBA — he was willing to run his statements nearly a week past their original due date. When we ran them together, 8,000+ statements batched correctly. We also verified the PDFs to make sure the output looked right. Everything was clean.

This customer was part of a large hospital organization. AR delays in a hospital environment are not just an inconvenience. They affect the timing of patient billing, which puts a strain on the relationship between the hospital and the people it serves. This customer had done a good job communicating with his patients about the delay and he thanked us for our efforts and transparency throughout the process.

I left the ticket in a hold state for several weeks until his next end of month cycle came around. I checked in with him after that run and all statements batched at the correct count. With his confirmation that everything was working as expected I closed the ticket.

I then took the issue upstream. I worked with the head of engineering to establish that prior to any future version release where a module was affected — and by extension its stored procedure — proper testing had to be part of the release process. I also created internal documentation requiring that any AR issue or web application related issue include the software version in the ticket from the start.

The most significant outcome was that discovering the stored procedure had not been updated with the patch allowed us to identify other customers on the same version before they experienced the same problem. Their upgrades were delayed until the corrected stored procedure could be formally included in the patch, protecting them from the same month end disruption.

---

*Robert de Mattos | robertdemattos@yahoo.com | linkedin.com/in/robert-de-mattos-16b8ab5*

