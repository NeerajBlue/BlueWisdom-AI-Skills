# Blue Wisdom AI Skills Repository

This repository contains a curated collection of AI skills, designed to act as system prompts, custom instructions, and behavior guidelines across various AI platforms (Gemini, ChatGPT, Claude, Grok, Qwen, Kimi, Copilot, etc.). 

By maintaining these skills in a central repository, Blue Wisdom ensures consistency in brand voice, operational workflows, and strategic output regardless of the AI tool being used.

## 🗂️ Skill Directory

### Development & Technical
- **`bw-app-development`**: Global guidelines for developing web apps, forms, and HTML email notifications. Enforces mobile-first design, brand colors, and AI-contextualized responses.
- **`bw-assessment-architect`** *(Drafting)*: Generates OD workshop outlines, role-plays, and React code for digital interactive assessments based on client context.

### Sales & Communication
- **`bw-communications`**: Global guidelines for drafting Blue Wisdom communications (emails, proposals, WhatsApp messages) enforcing the BW tone and visual identity.
- **`bw-ld-proposal-generator`**: Generates A4 print-ready HTML L&D training proposals, automatically injecting company profiles, tiered pricing, and animations.
- **`bw-client-proposal-crafter`** *(Drafting)*: An advanced sales engine that extracts requirements from client inquiry emails and formulates multi-option strategic proposals.

### Operations & HR
- **`bw-hr-automation-bot`** *(Drafting)*: Manages Google Apps Scripts and Canva-style HTML email templates for automated, brand-aligned candidate responses.
- **`bw-trainer-ops-coordinator`** *(Drafting)*: Automates the management of the outsourced trainer pool via the `Trainers_Master_Tracker.xlsx`.

### Strategy & Research
- **`bw-strategic-okr-manager`** *(Drafting)*: The "CEO Assistant" skill. Tracks the 3-year growth plan, generates weekly task lists, and conducts operational reviews.
- **`bw-competitive-intelligence`** *(Drafting)*: Benchmarks offerings and UX features from global competitors (Korn Ferry, Gallup, McKinsey).
- **`bw-digital-asset-organizer`** *(Drafting)*: A utility for categorizing, renaming, and structuring scattered files into standard folder hierarchies.

## 🛠️ How to Use These Skills

### Using in Gemini (Local)
These skills are automatically picked up if they are located in your `~/.gemini/config/skills/` directory. Simply ask the Gemini agent to use a specific skill (e.g., "Help me write an email using the `bw-communications` skill").

### Using Across Other AI Platforms (ChatGPT, Claude, Grok, Qwen, Kimi, Copilot)
To use a skill in another platform:
1. Open the specific skill folder.
2. Open the `SKILL.md` file.
3. Copy the markdown content (ignoring the frontmatter at the top between the `---` dashes).
4. Paste the content into the "System Instructions" or "Custom Instructions" section of the target AI platform.
   - **ChatGPT**: Paste into "Custom Instructions" or build a Custom GPT.
   - **Claude**: Create a "Project" and paste into the "Project Instructions".
   - **Qwen/Kimi/Grok**: Use it as the primary system prompt at the beginning of a conversation.

## 🔄 Updating & Modifying Skills

To update a skill:
1. Edit the relevant `SKILL.md` file in this repository.
2. Commit and push the changes to GitHub.
3. If using across other platforms, you will need to manually copy-paste the updated instructions into those respective platforms.

## 🔍 Searching and Forking External Skills
You can expand this repository by exploring GitHub for existing prompts:
1. Search GitHub for repositories like `Awesome-ChatGPT-Prompts` or `AI-System-Prompts`.
2. Find a relevant prompt, create a new folder in this repository, and add it as a `SKILL.md` file following the standard format.
3. Refine the prompt to match Blue Wisdom's specific context and tone.
