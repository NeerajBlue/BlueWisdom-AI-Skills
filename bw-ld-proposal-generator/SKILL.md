---
name: bw-ld-proposal-generator
description: >-
  Generates an A4 print-ready HTML L&D training proposal for Blue Wisdom.
  Automatically injects company/trainer profiles, 10:20:70 methodology, CSS animations,
  tiered pricing, and generates context-relevant images using AI tools.
---

# Blue Wisdom L&D Proposal Generator

## Overview
This skill guides the agent to automatically generate premium, print-ready HTML training proposals for Blue Wisdom Pvt Ltd. It utilizes predefined HTML templates with CSS animations, standard methodology timelines, predefined company/trainer profiles, and uses image generation tools to inject high-quality visuals.

## Dependencies
- `generate_image` tool (Required to create relevant hero/cover illustrations).
- `write_to_file` tool (Required to output the HTML document).

## Workflow

### 1. Collect Details
If the user hasn't provided them, ask for:
- Client Name
- Training Topic / Title
- Target Audience & Batch Sizes
- Commercial Pricing (default to ₹35,000/day for classroom, but ask to confirm).

### 2. Generate Hero Illustration
Use your `generate_image` tool to create a relevant, beautiful illustration. 
- Example prompt: "Professional corporate training environment illustration, modern flat vector art, blue and white color palette, business professionals collaborating" or specific to the topic (e.g., "Leadership strategy").
- Save this image locally in the proposal folder.

### 3. Prepare the HTML Template
Read the master HTML template located at:
`C:\Users\neera\.gemini\config\skills\bw-ld-proposal-generator\resources\bw_master_template.html`

### 4. Inject Dynamic Content
Replace the `{{PLACEHOLDERS}}` in the HTML string with the client's information:
- `{{TITLE}}`, `{{CLIENT_NAME}}`, `{{TAGLINE}}`, `{{TARGET_AUDIENCE}}`, `{{DURATION}}`, `{{BATCH_SIZE}}`
- `{{BW_LOGO}}`: Replace with `<img src="blue_wisdom_logo.png" alt="Blue Wisdom">` (assume the file will be in the folder, or use `<h2>BLUE WISDOM</h2>` as a fallback).
- `{{CLIENT_LOGO}}`: Replace with the client's logo `<img>` if available, or text if not.
- `{{CONTEXT_HERO_IMAGE}}`: Replace with `<img src="your_generated_image.png" class="hero-image" alt="Training Context">` (using the image you generated in Step 2).
- `{{PILLAR_CARDS}}`: Generate 3-4 HTML blocks for the training need: `<div class="pillar-card"><h3>Title</h3><p>Desc</p></div>`
- `{{TIMELINE_ITEMS}}`: Generate the 10:20:70 timeline: `<div class="timeline-item"><div class="timeline-title">Step</div><div class="timeline-content">Desc</div></div>`
- `{{COMMERCIAL_TIERS}}`: Replace with the tiered pricing structure (Silver/Gold/Platinum) using the `.pricing-box` HTML structure.

### 5. Output Final File
Use the `write_to_file` tool to save the customized HTML string as `[Client_Name]_Proposal.html` in the user's current directory.

## Common Mistakes
- **Forgetting to invert the logo:** If placing a logo on the dark blue title page, ensure `filter: brightness(0) invert(1);` is applied via CSS if it's a dark logo.
- **Not using absolute paths:** If you generate an image, ensure you link it properly in the HTML so it renders when opened in the browser.
- **Skipping CSS classes:** Always use the predefined CSS classes like `.animate-up`, `.timeline`, and `.pillar-card` so the document maintains its polished look.
