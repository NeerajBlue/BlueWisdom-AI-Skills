---
name: bw-design-document-generator
description: Generates premium consulting-style Design Documents (DD) and Session Plans for Blue Wisdom, including context, objectives, modules, timelines, pre/post-assessments, and 30-60-90 day implementation plans.
---

# BW Design Document (Session Plan) Generator

## Overview
This skill generates industry-best, benchmarked (e.g., McKinsey/Big 4 style) Design Documents (DD) for Blue Wisdom training sessions. 
A Design Document is strictly a **Session Plan and Strategy Document**, NOT a proposal. **COMMERCIALS ARE NOT TO BE MENTIONED IN THE DESIGN DOCUMENT.**

## Structure of the Design Document
The output MUST be a highly professional, A4-ready HTML document containing the following sections:

1. **Cover Page**
   - Title MUST be "Design Document" (not proposal).
   - Specify if the session is Classroom or Digital, and state the duration (e.g., 1-Day, 3-Day).
   - Must include Blue Wisdom logo (`C:\Users\neera\OneDrive\Desktop\BW CEO\03_Marketing_and_Sales\Blue_Wisdom_Website\images\blue_wisdom_logo.png` or `bw-logo.png`).
   - Must include the Client Logo (use Wikipedia/Clearbit URLs if local is unavailable).
   - Use the `generate_image` tool to create a contextual cover illustration.

2. **Context & Background**
   - The organizational challenge and why this intervention is needed.

3. **Objectives & Value Proposition (Benefits)**
   - Clear, measurable learning and behavioral objectives.
   - Benefits for Participants (WIIFM) and Organization (ROI).

4. **Detailed Session Plan (Tabular Format)**
   - MUST include: Module, Topics, Sub-topics, Methodology, Duration, and Timelines.
   - For 1-Day sessions, use the standard 10:00 AM to 5:00 PM timeline (10:00-11:30 Mod 1, 11:30-11:45 Break, 11:45-13:15 Mod 2, 13:15-14:00 Lunch, 14:00-15:30 Mod 3, 15:30-15:45 Break, 15:45-17:00 Mod 4).

5. **Pre & Post Assessment Plan**
   - Include a pre-workshop assessment (Google Form link).
   - Include post-assessment metrics.

6. **Implementation & Training Effectiveness (30-60-90 Day Plan)**
   - **30 Days:** Immediate application, quick wins, initial follow-up.
   - **60 Days:** Habit formation, manager check-ins, advanced application.
   - **90 Days:** Sustained behavior change, measurable ROI, final effectiveness report.

7. **Recommendations for HR Head**
   - Provide strategic recommendations. For TTT programs, explicitly recommend: "Ideally TTT should be a minimum of 3 days with teach-back sessions and certifications."
   - Recommend "training delivery assessments" during the participants' live sessions to see the impact and training effectiveness.

8. **Consultant Profile**
   - Include the image of Neeraj Bhardwaj (`C:\Users\neera\OneDrive\Desktop\BW CEO\03_Marketing_and_Sales\Blue_Wisdom_Website\images\consultant-neeraj.jpg` or `Neeraj NB 2.jpeg`).

## HTML & Styling Rules (Zero-Overlap Print Architecture)
- Use premium CSS (modern tables, deep corporate blue `#00447C`, sans-serif typography).
- **CRITICAL RULE: NO ABSOLUTE POSITIONING FOR FOOTERS:** NEVER use `position: absolute; bottom: 0;` for footers on an A4 page! You MUST use a **Flexbox Page Architecture**.
- **Flexbox A4 Page Architecture:** Format strictly for A4 printing (`@page { size: A4; margin: 0; }`). Configure `.page` containers as Flexbox columns:
  ```css
  .page {
      width: 210mm;
      min-height: 297mm;
      height: 297mm;
      max-height: 297mm;
      padding: 0;
      page-break-after: always;
      box-sizing: border-box;
      position: relative;
      background-color: #ffffff;
      margin: 40px auto;
      box-shadow: 0 10px 25px rgba(0,0,0,0.3);
      overflow: hidden;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
  }
  .page-content { padding: 20px 45px 15px 45px; flex-grow: 1; overflow: hidden; box-sizing: border-box; }
  .frozen-header { flex-shrink: 0; width: 100%; box-sizing: border-box; }
  .frozen-footer { flex-shrink: 0; margin-top: auto; display: flex; width: 100%; box-sizing: border-box; }
  @media print {
      @page { size: A4; margin: 0; }
      html, body { background: none; margin: 0; padding: 0; -webkit-print-color-adjust: exact; print-color-adjust: exact; }
      .page { box-shadow: none; margin: 0; width: 210mm; height: 297mm; max-height: 297mm; overflow: hidden; page-break-after: always; page-break-inside: avoid; border: none; display: flex; flex-direction: column; justify-content: space-between; }
  }
  ```
- **Mandatory Global Typography & Spacing Compression:** Enforce `line-height: 1.45;`, `font-size: 12.5px;` for body text, `table { margin: 8px 0; font-size: 11.5px; } th, td { padding: 6px 8px; }`, and `.card { padding: 10px 12px; }`.
- **Strict Content Budget & Vertical Audit per Page:** Keep content inside `.page-content` below **650px – 700px** out of the 967px available. Never stack large tables with decorative boxes on the same page. Always audit every page before finalizing to guarantee **280px to 600px of clean whitespace above the footer**.
- Do NOT include any pricing or commercial tiers.
