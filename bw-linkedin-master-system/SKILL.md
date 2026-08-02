---
name: bw-linkedin-master-system
description: "Master system for all Blue Wisdom LinkedIn operations. Integrates content strategy, automated lead generation, image generation, and trainer requisitions."
---

# Blue Wisdom LinkedIn Master System

This skill integrates all LinkedIn-related workflows for Blue Wisdom into a single cohesive strategy. Whenever you are asked to generate a LinkedIn post, manage LinkedIn leads, or handle LinkedIn-related image generation, strictly follow these rules.

## 1. Content Strategy & Copywriting
- **Brand Ethos:** "It's not just business, it's about genuine human connection." Posts should reflect trust, thought leadership, and Organizational Development (OD) expertise.
- **The 6x6 Rule:** Keep paragraphs short (maximum 6 lines). Use plenty of whitespace.
- **Tone:** Professional, deeply insightful, warm, and engaging. Never use excessive emojis or overly casual slang.
- **CTAs:** End every post with a clear Call to Action (e.g., inviting comments, asking a thought-provoking question, or directing to a specific BW landing page).

## 2. Lead Generation & Automation
- **The Engine:** Blue Wisdom uses a custom local automation suite located in `C:\Users\neera\OneDrive\Desktop\Social Media`.
- **Top of Funnel (Hunting):** Run `lead_scraper.py` while attached to the user's Chrome remote debugging port to scrape names and URLs from LinkedIn search results into `lead_database_updated.csv`.
- **Execution (Messaging):** Run `lead_generator.py` to automatically dispatch connection requests and personalized "Day 1 Messages" using the local browser.
- **Tracking:** Use `launch_dashboard.py` to generate and view the Visual HTML Dashboard to track daily progress.

## 3. Visuals & Image Generation
- **Aesthetic:** Strictly adhere to the Blue Wisdom visual identity (Deep Corporate Blue and Gold/Yellow, glassmorphism UI where applicable).
- **Portraits:** When generating images of executives or the CEO (Neeraj), they MUST be photorealistic, high-quality, and depict a fair-skinned Indian/Asian professional in a corporate setting. (Refer to the `bw-consistent-portrait-generator` skill for Midjourney/Stable Diffusion prompt structures).
- **Canva Integration:** Prefer using established Canva templates for standard greetings/announcements. The agent can use the `browser` subagent to fetch Canva links.

## 4. Trainer Requisitions (Hiring)
- When posting a requirement for outsourced trainers on LinkedIn, use a structured format:
  1. **The Hook:** A clear statement of the requirement (e.g., "Seeking an expert Leadership Trainer for a 2-day intervention").
  2. **The Details:** Location, Audience Level (e.g., Mid-Management), Topic, and Dates.
  3. **The Call to Action:** Ask interested trainers to DM their profiles or fill out a specific BW assessment form.
  4. **Hashtags:** #BlueWisdom #TrainerJobs #ODInterventions #LeadershipDevelopment

## General Rule
If a user requests a LinkedIn task, first identify which of the 4 pillars (Content, Lead Gen, Visuals, Hiring) it falls under, and apply the rules above systematically.
