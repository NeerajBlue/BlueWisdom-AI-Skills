---
name: bw-consistent-portrait-generator
description: Generates high-quality images of Neeraj Bhardwaj with strictly consistent facial features across diverse outfits, locations, and environments. Includes cross-platform AI instructions (Midjourney, Stable Diffusion).
---

# BW Consistent Portrait Generator

This skill is designed to generate images of Neeraj Bhardwaj where the **outfit, location, environment, and lighting can change entirely**, but the **facial features remain strictly consistent**. 

It serves as a master guide for generating assets for presentations, social media, and marketing, and includes clear instructions for using this consistency system across different AI platforms.

## 1. The Standard Reference Image
For platforms that support image prompting (like Midjourney's `--cref` or Stable Diffusion's FaceID), you must ALWAYS use the official Standard Reference Image to anchor the AI to the correct face.

**Master Reference Image Path:**
`C:\Users\neera\OneDrive\Desktop\NB\ChatGPT Image Apr 28, 2026, 09_36_45 PM.png`

## 2. The Locked Facial Prompt Block
Whether you are using image referencing or pure text generation, you must ALWAYS include this exact text block in your prompt to enforce facial consistency. Do not alter these words.

> **[LOCKED_FACE_BLOCK]:** "A distinguished South Asian man in his late 40s. FACE: medium-brown skin tone with hyper-detailed texture, warm brown expressive eyes, dark neatly combed hair with slight graying at temples, prominent thick dark well-groomed mustache, small goatee below lower lip. No full beard, no clean-shaven."

## 3. Platform-Specific Instructions

### For Midjourney (Discord/Web)
Midjourney handles character consistency exceptionally well using the `--cref` (Character Reference) parameter.
1. Upload the **Master Reference Image** to Discord and get its URL.
2. Structure your prompt: `/imagine prompt: [LOCKED_FACE_BLOCK] wearing [Outfit] in [Location], [Lighting/Style] --cref [URL_of_Master_Reference_Image] --cw 100`
3. *Note:* `--cw 100` tells Midjourney to capture the face perfectly. If you want to change the hair significantly, use `--cw 0` (focuses purely on the face).

### For Stable Diffusion (A1111 / ComfyUI)
Use the **IP-Adapter FaceID** or **ReActor** extension.
1. Load the **Master Reference Image** into the FaceID/ReActor node.
2. In your positive prompt, include the `[LOCKED_FACE_BLOCK]` alongside your new outfit/environment description.
3. Keep the denoising strength between 0.4 and 0.6 to allow the new environment to blend naturally with the swapped face.

### For DALL-E 3 / Nano Banana (Text-to-Image Only)
If you cannot use an image reference, you must rely entirely on the prompt formula.
**Formula:** `Photorealistic 8K portrait. [LOCKED_FACE_BLOCK]. He is wearing [Outfit]. He is located in [Environment]. [Lighting conditions], [Camera lens, e.g., 85mm f/1.4].`

---

## 4. Standard Templates

### Template 1: The "Images (1)" Style (User Requested)
Based on your reference `images (1).jpg`.
**Prompt Construction:**
`Photorealistic 8K portrait. [LOCKED_FACE_BLOCK]. He is wearing a sharp, tailored executive suit with a subtle pattern. He is located in a high-end, modern corporate boardroom with glass walls overlooking a cityscape. Natural bright daylight streaming in, cinematic lighting, shot on 85mm lens. Engaging, confident expression.`

### Template 2: Casual Friday Coaching
**Prompt Construction:**
`Photorealistic 8K portrait. [LOCKED_FACE_BLOCK]. He is wearing a high-quality smart-casual navy polo shirt. He is sitting in a vibrant, modern coffee shop with blurred background elements. Warm, inviting cafe lighting, shallow depth of field. Smiling, approachable expression.`

### Template 3: Keynote Speaker
**Prompt Construction:**
`Photorealistic 8K portrait. [LOCKED_FACE_BLOCK]. He is wearing a dark blazer over a crisp white shirt (no tie) with a small Blue Wisdom lapel pin. He is standing on a dark, dramatic keynote stage. Dramatic spotlighting illuminating his face, blurred audience in the deep background. Gesturing dynamically with one hand, energetic expression.`
