# Unified Support Context: A Concept for AI-Powered Case Summarization

**Concept by Robert de Mattos**
*19+ years in technical and customer support, including tiered SaaS support, field hardware, and startup environments*

---

## The Problem

Support agents work across multiple tools simultaneously. A single customer issue can generate activity in a ticketing system like Zendesk, a project tracker like Jira, an internal messaging platform like Slack or Microsoft Teams, and email. Each of those tools captures a piece of the story but none of them captures all of it.

When an agent returns from vacation, picks up a handed off case, or needs to brief a stakeholder, they face the same problem every time. The information exists but it is scattered. Getting up to speed means digging through ticket comments, scrolling through Slack threads, checking Jira updates, and reading email chains. That process takes time, misses context, and relies entirely on the individual agent's memory and organizational habits.

The problem compounds when the audience changes. A support agent needs operational detail. A support leader needs enough context to add expertise or make a decision. An engineer needs a technically precise summary. A Customer Success professional needs to understand customer impact. A CEO needs the thirty second version. Right now none of them get what they actually need without someone manually translating the full story for each audience.

Context also gets lost permanently. The ideas that came up in a Slack thread, the suggestion an engineer made that was almost right, the note a colleague left that explains why a particular approach was abandoned — these things disappear because no single tool captures all of them and no agent has time to synthesize them manually.

---

## The Idea

A summarization application powered by artificial intelligence that uses API connections to gather information from the tools a support team already uses and synthesizes everything related to a specific customer issue into a single unified context. The application's chief function is AI-driven summarization — taking scattered information from multiple sources and using large language model technology to produce a clear, accurate, role-specific briefing on demand. The AI does not replace the agent's judgment. It removes the burden of manually piecing together context so the agent can focus on what only a human can do.

### What It Gathers

The application connects via API to the following platforms:

- **Zendesk** — ticket notes, agent comments, status history, escalation records, and resolution documentation
- **Jira** — engineering tickets, bug reports, linked issues, and developer comments related to the customer case
- **Slack / Microsoft Teams** — internal conversations related to the customer issue, including suggestions, decisions, and context that never made it into the formal ticket
- **Salesforce** — critical customer account information including how much the customer pays for the application, which features they use most, how they currently feel about the relationship, and notes from Customer Success interactions before and after a technical issue impacted them

### What It Produces

The application generates role-specific summaries on demand so that the right person gets the right level of detail without having to read everything.

**For a returning agent or any agent seeking case context**
A plain language summary of everything that happened on a case including what was tried, what worked, what didn't, and what still needs to happen next. This applies equally to an agent returning from vacation, an agent picking up a handed off case, or any agent who wants to understand a case they were never involved in — whether it is still ongoing or has already been resolved.

**For an engineer receiving an escalation**
A technically precise handoff document with reproduction steps, what was already attempted, relevant error context from the ticket, and what the agent believes is happening at the system level.

**For a support leader**
A full timeline with key decision points highlighted so they can add their expertise or make a decision without reading every comment in the ticket.

**For a Customer Success professional**
A customer impact summary that connects the technical issue to the broader relationship including how the customer felt before the issue, what CS has communicated since, and what the current relationship status looks like based on Salesforce notes.

**For a CEO or executive**
A three to five sentence version that explains what happened, how it was resolved or where it stands, and what it means for the customer relationship and business impact.

---

## Why the Salesforce Integration Matters

Connecting customer account data to the support context changes how every briefing is framed. An agent, leader, or executive receiving a summary would not just understand what the technical issue is. They would understand who the customer is, what the business relationship looks like, how much revenue is at risk, which features the customer depends on most, and how Customer Success has been managing the relationship around the issue.

That context changes decisions, escalation urgency, and communication tone at every level of the organization. A $500,000 account experiencing a recurring issue that CS has been managing for months tells a very different story than the ticket alone would suggest.

---

## How It Would Work

The application functions as an API bridge connecting the tools support teams already use rather than replacing them. It does not require agents to change their workflow. They continue working in Zendesk, Slack, Jira, and Salesforce as they always have. The application runs in the background, continuously gathering and indexing activity related to each customer issue.

When a briefing is needed the agent, leader, or executive selects the customer case, chooses their role, and the application generates a summary tailored to their needs. No digging. No scrolling. No lost context.

---

## Why This Matters

Support agents spend significant time getting back up to speed on work they have already done or work a colleague handed off. That time is invisible. It does not show up in any metric and it is not counted as productive work. But it compounds across every agent on every shift and represents a meaningful loss of capacity in every support organization.

Beyond productivity the bigger loss is context. When context is lost decisions get made without full information, customers have to repeat themselves, and the institutional knowledge that lives in scattered conversations disappears the moment the people involved move on.

This application ensures that context is never lost.

---

## A Note on Execution

This is a concept document, not a technical specification. The author is not an engineer and would not build this application independently. What the author can articulate clearly is how it would need to work from a functional standpoint, because the problem it solves comes from 19 years of lived experience across three distinct support environments.

The first eleven years were spent in field hardware support at NCR Corporation across Charlotte, Omaha, and New Orleans. Context mattered even then. A level 3 engineer making a recommendation to a field technician without knowing the full history of that machine, what had already been attempted, and what the customer environment looked like was working without the full picture. Had AI summarization existed in that environment, level 3 agents could have made more precise recommendations, field technicians could have arrived on site better prepared, and retail and bank customers would have experienced less downtime from repeat visits. The following six and a half years were spent in tiered SaaS support at Emporos Systems, a healthcare software company. In between, the author served as the founding North American customer support resource at Instagrid, a physical product startup where warranty support, repair coordination, and application guidance all lived in separate places. Even in that smaller environment the problem was the same. A repair technician, an application engineer, and a customer facing support resource each held a piece of the customer's story. There was no single place to bring those pieces together. This concept would have worked there too, scaling down to a startup just as naturally as it scales up to an enterprise.

At a functional level the application would require API connections to Zendesk, Jira, Slack, Microsoft Teams, and Salesforce to pull both structured and unstructured data related to a customer issue. That data would be fed into a large language model capable of generating coherent, role-specific summaries on demand. The engineering execution would belong to a development team. The domain expertise — knowing what needs to be built, why it matters, who it serves, and what each role-specific briefing needs to contain — belongs to the people who have spent careers in support.

This concept exists because the people who build tools often need the people who use them to explain the problem clearly enough that the right solution can be designed. That is the intent of this document.

---

*Robert de Mattos | robertdemattos@yahoo.com | linkedin.com/in/robert-de-mattos-16b8ab5*
