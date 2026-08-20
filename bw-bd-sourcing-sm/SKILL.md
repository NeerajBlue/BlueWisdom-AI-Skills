---
name: bw-bd-sourcing-sm
description: "Scans WhatsApp and LinkedIn for Blue Wisdom training, coaching, and consulting opportunities. Extracts leads and formats them for outreach."
---

# Blue Wisdom Social Media BD Sourcing

This skill automates the repetitive task of searching for Business Development (BD) opportunities across WhatsApp and LinkedIn that match Blue Wisdom's service offerings.

## Trigger
Use this skill when the user asks to "scan for opportunities", "source leads", or "find training/coaching requirements on social media".

## Prerequisites
1. The user must have Chrome running with remote debugging enabled (via `Start_Chrome_Automation.bat` or similar), logged into WhatsApp Web and LinkedIn.

## Execution Flow

### 1. WhatsApp Search
Use the `browser` subagent to navigate to `https://web.whatsapp.com/`.
- Locate the "Search or start a new chat" textbox.
- Sequentially search for keywords:
  - "trainer required"
  - "looking for coach"
  - "consulting opportunity"
  - "L&D requirement"
- Check the "Messages" section of the search results.
- Extract the exact text, sender, and group name of relevant posts from the past 48 hours.

### 2. LinkedIn Search & Automated Outreach
Use the `browser` subagent to navigate to `https://www.linkedin.com/`.
- Use the global search bar to search for: `("looking for" OR "hiring") AND ("corporate trainer" OR "leadership coach" OR "OD consultant")`.
- Filter the results by **Posts** and sort by **Past week** or **Latest**.
- Extract the text, author, and link of 3-5 relevant posts where someone is actively looking to hire or source a professional in Blue Wisdom's domain.
- **IMMEDIATE OUTREACH**: For each relevant LinkedIn opportunity found, the agent MUST immediately navigate to the author's profile.
  - If the "Connect" button is available, click it and send a personalized connection request mentioning their requirement and how Blue Wisdom can help.
  - If they are already a 1st-degree connection, click "Message" and send a direct response to their requirement.

### 3. Consolidation & Formatting
Compile the scraped opportunities from both platforms into a structured Markdown digest:

```markdown
# Daily BD Sourcing Report

## WhatsApp Opportunities
* **[Group/Sender]**: [Snippet of requirement]
  * **Action**: [Suggest outreach step, e.g., "WhatsApp message to +91..."]

## LinkedIn Opportunities
* **[Author Name]** ([Link to post]): [Snippet of requirement]
  * **Action**: [Suggest outreach step, e.g., "Send InMail or comment"]
```

### 4. Next Steps
Present the digest to the user and offer to:
1. Automatically draft outreach emails/messages for these specific opportunities.
2. Log these into the `lead_database_updated.csv` file for pipeline tracking.
