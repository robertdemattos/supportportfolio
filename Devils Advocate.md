# Using AI as a Devil's Advocate in Troubleshooting

One of the most common traps in technical support is pattern recognition working against you. When an issue looks like something you have fixed a hundred times before your brain moves quickly toward the familiar solution. That confidence is earned through experience but it can also cause you to miss something that doesn't fit the pattern.

This document walks through a real troubleshooting scenario where the standard fix failed, the agent repeated the same approach with the same result, and the actual cause turned out to be something that only became visible when someone asked the right question. It then demonstrates how an AI tool could have surfaced that question earlier in the process.

---

## The Scenario

A customer had an unprocessed transaction stuck in the system. The standard fix for this type of issue was to copy the XML data for a signature called mailout and run it through the tester to repair the data that had caused the transaction to get stuck.

Before running the fix the agent reviewed the XML carefully, checking for duplicate form brackets in the layout as standard practice. None were found. The fix was applied. It failed.

The agent pulled the original broken XML and worked through it again from the beginning. Same result.

At this point the agent brought in a colleague who asked one question. Had you checked SQL?

When the agent looked in SQL it became clear that the incomplete transaction had already captured the signature. The XML did not need to be populated at all. The actual fix was to leave the signature bracket empty. The assumption that the XML needed to be corrected was wrong because the data that would normally be missing was already there in the database.

---

## Where AI Could Have Helped

After the first failed attempt and before repeating the same approach the agent could have used an AI tool to challenge the assumption. Here is what that prompt could have looked like.

---

## The Prompt Given to AI

*"I am troubleshooting an unprocessed transaction that is stuck in our system. The standard fix is to copy the XML data for a signature called mailout and run it through the tester. I checked the XML for duplicate form brackets as standard practice and found none. I applied the fix and it failed. I then pulled the original broken XML and tried again with the same result. I believe the issue is in the XML but I cannot figure out what I am missing. Can you help me think through other possible causes I may not have considered?"*

---

## The AI Output

> Based on what you have described here are some alternative possibilities worth investigating before assuming the issue is in the XML itself.
>
> **1. The data may already exist in the database.**
> Before assuming the signature data needs to be added check whether the incomplete transaction has already captured the signature at the database level. If SQL shows the signature was captured the fix may be to leave the signature bracket empty rather than populate it. Populating a field that already has data at the database level could be causing the conflict.
>
> **2. The tester environment may not reflect the current state of the transaction.**
> If the tester is pulling from a cached or slightly delayed version of the transaction data it may not be showing you what is actually in the system right now. Verify that the tester is reading the current state before assuming the XML is the source of the problem.
>
> **3. There may be a downstream dependency causing the transaction to remain stuck.**
> The transaction may be waiting on something outside the XML entirely such as a process, a service, or a job that has not completed. Check whether anything else in the workflow needs to complete before this transaction can move forward.
>
> **4. The fix may have been applied correctly but requires a trigger to take effect.**
> In some systems a corrected transaction does not automatically reprocess. It may need to be manually requeued or a specific process may need to be restarted to pick it up.

---

## What Changed

The first alternative the AI surfaced — checking whether the data already existed in SQL — was the actual cause. Had the agent used this prompt after the first failed attempt they could have avoided repeating the same fix a second time and waiting for a colleague to ask the right question.

The AI did not know the system. It did not have access to the database or the tester. What it did was apply logical troubleshooting thinking to the description of the problem and surface possibilities the agent had not considered because the familiar pattern had narrowed their focus.

That is the value of using AI as a devil's advocate in troubleshooting. It does not replace technical knowledge. It challenges the assumptions that technical knowledge sometimes creates.

---

## The Takeaway

When a standard fix fails the instinct is often to try the same fix again more carefully. Before doing that paste your theory and your steps into an AI tool and ask it to challenge your assumption. The question it surfaces might be the one a colleague would have asked — and it is available at any hour without interrupting anyone.

---

*Robert de Mattos | robertdemattos@yahoo.com | linkedin.com/in/robert-de-mattos-16b8ab5*
