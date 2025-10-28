# Sora 2 + n8n: Hollywood-Quality Video Ad Generator

Turn a single product photo into a cinematic, high-converting video ad — powered by Sora 2, GPT-4o, Gemini 2.5 Pro, and n8n.

---

## Overview
This project automates the entire AI video ad creation pipeline.  
Upload a product photo → AI analyzes it → writes a cinematic prompt → generates a professional CGI video ad → uploads and stores everything automatically.

You’ll learn how to orchestrate AI video production using n8n, OpenRouter, Google Drive, Baserow, and Kie.ai’s Sora 2.

Perfect for AI automation engineers, no-code builders, and creative studios that want to scale ads with AI.

---

## How It Works

### 1. Form Submission
Trigger: `FormTrigger` node  
Collects:
- Product photo  
- Aspect ratio (portrait or landscape)  
- Short description  

Uploads instantly start the workflow.

---

### 2. Upload to Google Drive
The uploaded photo is saved in a “Product Photos” Drive folder.  
A shareable link (`webContentLink`) is passed forward for analysis and Sora input.

---

### 3. Product Image Analysis (GPT-4o)
GPT-4o performs a YAML-based structured analysis of the product image:
- Ignores background and props  
- Extracts materials, colors (with HEX codes), textures, and logos  
- Outputs an exhaustive YAML object describing only the product  

This gives later nodes a complete understanding of the subject.

---

### 4. Creative Direction (Gemini 2.5 Pro)
Gemini generates a Sora 2-compatible cinematic timeline prompt:
- Defines Vibe, Format, and Genre  
- Writes a 0–12s Timeline Breakdown:
  - [0–3s] Hook  
  - [3–6s] Context  
  - [6–9s] Climax  
  - [9–12s] Resolution  
- Includes camera motion, lighting cues, emotion, and sound design  

This step turns raw data into a film director’s script.

---

### 5. Sora 2 Video Generation (via Kie.ai)
The cinematic prompt, image URL, and aspect ratio are passed into the  
“Kie.ai Sora 2 Image → Video” workflow, which returns a CGI-style product ad.  

Result: A cinematic, UGC-style commercial generated in minutes.

---

### 6. File Management
- Video is downloaded via HTTP Request node  
- Uploaded to Google Drive “Product Videos” folder  
- Metadata (image, video, status, description) logged in Baserow  

Every output is archived, searchable, and ready to share.

---

## Tech Stack
| Tool | Purpose |
|------|----------|
| n8n | Workflow orchestration |
| Sora 2 (Kie.ai) | Text-to-video generation |
| GPT-4o | Image analysis and YAML output |
| Gemini 2.5 Pro | Creative direction and timeline prompt |
| Baserow | Data logging and asset management |
| Google Drive | File storage |

---

## Repository Contents
| File | Description |
|------|-------------|
| `47_AI Ads Sora.json` | Main n8n workflow file |
| `README.md` | Documentation (this file) |

---

## Setup

### 1. Clone the Repository

### 2. Import Workflow into n8n

- Open your **n8n dashboard**  
- Click **Import Workflow** → upload `47_AI Ads Sora.json`

---

### 3. Configure Credentials

Add the following integrations:

- **OpenRouter API** (for GPT-4o + Gemini 2.5 Pro)  
- **Kie.ai** (Sora 2 endpoint)  
- **Google Drive OAuth2**  
- **Baserow API**

---


### 4. Deploy

- Run the workflow once to generate your unique **Form URL**  
- Upload a product photo and watch your cinematic ad appear in your Drive


---

📧 **Email me directly**: contact@loopsera.com
For quick questions, customisation requests, or workflow troubleshooting.

🌐 **Visit my website**: [https://loopsera.com](https://loopsera.com)
Explore more automation templates, services, and case studies.

📞 **Book a Discovery Call**: [https://cal.com/loopsera/discoverycall](https://cal.com/loopsera/discoverycall)
For businesses that need a custom AI solutions built.

🎓 **1-on-1 Coaching Session**: [https://cal.com/loopsera/n8n-ai-agent-coaching-session](https://cal.com/loopsera/n8n-ai-agent-coaching-session)
Personalised coaching to help you build, troubleshoot, or optimise n8n AI workflows. Perfect for both beginners and advanced users.

💬 **Join the AI Builder’s Boardroom (Skool Community)**: [https://www.skool.com/ai-builders-boardroom-1717](https://www.skool.com/ai-builders-boardroom-1717) — a professional community for builders creating AI agents that talk, listen, and sell, focused on deploying the digital workforce of the future.
