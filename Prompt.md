# Codex Career Plan — Prompt System

**How to use this (token strategy):**

1. Save `CONTEXT.md` (below) as a real file in your vault folder. Paste its content into Codex **once**, at the start of session 1, or just tell Codex to read it from disk.
2. Run each numbered Step as a **separate Codex prompt/session**. Each step tells Codex which specific files to open itself (so you don't paste file contents into the prompt, saving tokens).
3. Each step ends by having Codex **write its output to a new file** (e.g. `01-upwork-profile.md`). If your account/tokens run out, your next session (even on a different OpenAI account) just re-reads `CONTEXT.md` + the output files already produced. Nothing is lost.
4. Do NOT run steps back to back in one giant session. One step = one focused Codex run.

---

## CONTEXT.md (persist this file, paste/reference once)

```
I am a full-stack freelance developer (Python, Django, Wagtail, React, Next.js) with 5-star Upwork feedback but low total revenue. I have $5k debt and need income fast. Goal: rebuild a disciplined freelance/consulting business with daily accountability, not scattered learning.

Expanding into: Claude/AI-agent skill building, model/agent/prompt distillation, fine-tuning, RAG pipeline development, OpenClaw agent building, MCP server integration, AI workflow automation (and non-AI automation), positioned as a Gen AI Consultant alongside my existing Django/Wagtail work.

Vault path: /home/imtiapy/Desktop/vault/work.md/Upwork & Freelancing/
Files in that folder Codex should read as needed (do not paste contents, just open path):
- 15 tips to make your profile standout by upwork community.md
- How to create proposal by upwork community.md
- Professional headline example by upwork community.md
- Upwork Profile examples for freelance beginners by upwork community.md
- Upwork profiles for top rated freelancers my research.md
- Upwork proposal sample by upwork community.md
- Current Upwork description my profile.md
- Freelance career blueprint.md
- Freelance focus plan.md
- Upwork profile analysis - AI Automation competitors.md
- My Client Feedback on Upwork.md

Constraints: keep every output concrete and actionable, no generic advice, no filler. Assume I have limited free-tier tokens, so be concise.
```

---

## Step 1 — Upwork Profile Rewrite

```
Read /home/imtiapy/Desktop/vault/work.md/Career-Plan/context.md. Then open only these files from the the following directory: /home/imtiapy/Desktop/vault/work.md/Upwork_and_Freelancing

"Current_Upwork_description.md", "Upwork_profile_analysis_AI_Automation_competitors.md", "My_Client_Feedback_on_Upwork.md", "Professional_headline_examples_by_upwork_community.md".

Task: Rewrite my Upwork profile.
1. One title/headline combining my Django/Wagtail expertise + emerging Gen AI consulting angle.
2. A keyword map for SEO: list target keywords for each of these sections separately: Title, Description, Portfolio titles, Portfolio descriptions, Skills, Other experience, Education, Certifications, Video intro title.
3. Full profile description (Hormozi-style hook opening, proof via my feedback, clear offer, CTA).

Save output to: "01-upwork-profile.md" in the following directory: /home/imtiapy/Desktop/vault/work.md/Career-Plan

DONE
```

---

## Step 2 — Grand Slam Offer + LinkedIn Positioning

```
Read /home/imtiapy/Desktop/vault/work.md/Career-Plan/context.md. and /home/imtiapy/Desktop/vault/work.md/Career-Plan/01-upwork-profile.md. 
Open /home/imtiapy/Desktop/vault/work.md/Upwork_and_Freelancing/My_Client_Feedback_on_Upwork.md for proof points.

Task: Act as Alex Hormozi. Build one Grand Slam Offer for my strongest current service (Wagtail CMS development) that I can reuse across Upwork, LinkedIn, and cold outreach.
Include: core promise, 3-4 bonuses, value stack with rough dollar values (target 10x perceived value vs my price), guarantee, and a one-paragraph LinkedIn bio using this offer.

Save output to: "02-offer-and-linkedin.md" in the following directory: /home/imtiapy/Desktop/vault/work.md/Career-Plan

DONE
```

---

## Step 3 — Daily Operating System

```
Read /home/imtiapy/Desktop/vault/work.md/Career-Plan/context.md, and (01-upwork-profile.md and 02-offer-and-linkedin.md from the /home/imtiapy/Desktop/vault/work.md/Career-Plan directory.)

Task: Design a simple daily routine/accountability system for a solo freelancer rebuilding income under time pressure. Include:
- A fixed daily time-block schedule (deep work, outreach, content, learning capped at X minutes to prevent tutorial-hopping)
- A weekly checklist (proposals sent, outreach sent, posts published, learning applied)
- One simple tracking method I can maintain in a markdown file or spreadsheet

Save output to: "03-daily-system.md" in the following directory: /home/imtiapy/Desktop/vault/work.md/Career-Plan

DONE
```

---

## Step 4 — Content & Outreach Engine

```
Read /home/imtiapy/Desktop/vault/work.md/Career-Plan/context.md and /home/imtiapy/Desktop/vault/work.md/Career-Plan/02-offer-and-linkedin.md.

Task: Build a lightweight weekly content and outreach plan across LinkedIn, Reddit, X, YouTube, cold outreach, and warm outreach (past clients). For each channel give: posting frequency, 3 content angle examples tied to my offer, and one outreach message template (cold and warm, short).

Save output to: "04-content-outreach.md" in the following directory: /home/imtiapy/Desktop/vault/work.md/Career-Plan

DONE
```

---

## Step 5 — Gen AI Consultant Roadmap

```
Read /home/imtiapy/Desktop/vault/work.md/Career-Plan/context.md.

Task: Turn my "expanding into" list (Claude/agent skills, distillation, RAG, MCP servers, OpenClaw, AI workflow automation, Gen AI consulting) into a realistic, prioritized 90-day learning-to-earning roadmap. Rank by fastest path to paid work given my existing Django/Wagtail base. Flag which skills to skip for now to avoid wasted learning time.

Save output to: "05-genai-roadmap.md" in the following directory: /home/imtiapy/Desktop/vault/work.md/Career-Plan
```