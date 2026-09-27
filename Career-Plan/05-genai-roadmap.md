# 90-Day GenAI Learning-to-Earning Roadmap

## Decision: sell implementation first, not “GenAI consulting”

Your fastest route to cash is **Django/Wagtail work with a narrowly scoped AI automation or knowledge-search add-on**. You already have credible delivery skills, 5-star feedback, and a concrete Wagtail offer. Do not pause outreach to become an AI generalist.

For the next 90 days, use this positioning:

> Django/Wagtail developer who builds practical AI-assisted workflows and private knowledge search for existing business systems.

The business outcome is the product: fewer manual admin hours, faster lead follow-up, or reliable answers from approved documents. “Claude,” “RAG,” and “agents” are implementation details.

## Priority ranking: fastest path to paid work

| Rank | Skill / service | Why it can sell now | First paid scope | Learn-to-sell threshold |
| --- | --- | --- | --- | --- |
| 1 | **AI workflow automation** (Django/Python + APIs; optionally n8n) | Direct ROI, small scopes, and naturally fits existing apps and integrations. | Lead intake: form/email → extract/classify → CRM task + draft reply + human approval. **$500–1,200** | Build one reliable workflow with logs, retries, approval step, and handover. |
| 2 | **Claude/OpenAI integration in Django** | This is an extension of work you already sell: admin tools, dashboards, CMS, APIs. | Add AI-assisted drafting, summarization, content tagging, or support-reply drafts to an existing Django app. **$750–1,500** | Secure server-side API use, structured outputs, prompt/version storage, cost limits, and evaluation examples. |
| 3 | **Small RAG / document knowledge assistant** | A visible, understandable pain point for teams with scattered policies, product docs, or internal manuals. | Upload approved documents; staff ask questions; answers cite sources; admin can refresh content. **$1,200–2,500** | Deliver citations, permissions, ingestion/re-indexing, “I don’t know” behavior, and 20-question evaluation set. |
| 4 | **AI discovery / workflow blueprint** | Paid diagnostic is useful after you can demonstrate the first three; it creates implementation work. | 90-minute workshop + workflow map + prioritized implementation brief. **$250–500**, credited toward build | Complete 3 discovery calls and use a repeatable audit template. |
| 5 | **MCP server integration** | Useful differentiator for connecting AI tools to a client’s systems, but most buyers purchase the workflow outcome, not MCP. | Expose one safe read-only internal action/tool to an approved AI client. **$1,000–2,000** | Authentication, least privilege, audit logs, rate limits, and clear tool descriptions. |
| 6 | **Claude / agent skills** | Helpful for your own delivery speed and reusable client playbooks; weak as a standalone beginner offer. | A documented internal content/research/support workflow with review gates. Bundle into automation work. | Create 2 reusable skills/playbooks that save your own time and are tested on real inputs. |
| 7 | **Distillation / fine-tuning** | Usually premature: needs high-quality examples, evaluation discipline, budget, and enough volume to justify it. | Only assess after a client has a repeatable high-volume task and baseline prompt data. | Do not sell in this 90-day period. |
| 8 | **OpenClaw agent building** | Tool-specific demand and client trust are less reliable than standard web/API automation; it risks platform-led learning. | None initially. Use only if a paying client specifically requires it. | Do not allocate scheduled learning time. |

## What to skip for now

Do **not** spend your next 90 days on:

- Fine-tuning or model distillation courses, datasets, or experiments. You do not yet have a client use case, labelled examples, or paid volume that makes them economical.
- Autonomous multi-agent systems, agent frameworks, or “agent swarms.” They add failure modes before you have paid, repeatable workflows.
- OpenClaw-specific building unless it appears in a qualified client request. Learn transferable API, security, and workflow patterns instead.
- Building a generic public chatbot SaaS, a broad AI portfolio site, or more than two demos. They delay conversations with buyers.
- Certifications without a demo, a proposal, or an outreach asset produced from them.

## Operating rule

Keep **70% of weekday business time on revenue activity** (proposals, outreach, calls, delivery) and **30% on targeted learning/building**. If debt pressure requires more immediate work, protect the revenue block first. Learning only counts when it produces a demo, reusable component, proposal sentence, or client-facing checklist.

## Before Day 1: choose two repeatable offers

Keep the existing Wagtail CMS Launch Sprint as the primary offer. Add only these two GenAI-adjacent offers:

### 1. AI Workflow Pilot — $750 fixed price

For a service business or existing web app with one repetitive admin workflow.

- One trigger (form, inbox, webhook, or scheduled job)
- One AI task (extract, classify, summarize, or draft)
- One destination (CRM, spreadsheet, database, Slack/email, or Django admin)
- Human approval before consequential external action
- Basic logs, failure notification, and 7-day bug-fix window
- Delivery target: 5 business days

Do not promise a fully autonomous employee. State the measurable saved step, for example: “turn incoming leads into a structured, reviewed CRM record in under five minutes.”

### 2. Private Knowledge Search Pilot — $1,500 fixed price

For a small team that repeatedly searches approved PDFs, docs, FAQs, or product material.

- Up to 100 agreed source files / pages
- Authenticated staff access
- Ingestion and refresh path
- Answers with links/citations to source passages
- Clear no-answer fallback
- 20 agreed test questions and short handover
- Delivery target: 10 business days

Exclude custom SSO, multi-tenant billing, uncontrolled web search, complex permissions, and guarantees of factual perfection. Quote them separately.

## Days 1–30: prove and sell the easiest implementation

### Week 1 — package and build the automation demo

**Outcome:** one demo that looks like a client deliverable, not a tutorial.

1. Pick one vertical-adjacent use case: agency lead intake, professional-services inquiry intake, or content approval. Choose the one closest to people you can contact now.
2. Build it in Django/Python first; use n8n only where it speeds integration. Flow: inbound form/email → validation → structured AI extraction → confidence/exception routing → human review → CRM/email action.
3. Add essentials: environment-based secrets, request IDs, raw-input retention policy, failure logging, retry-safe writes, cost cap, and an explicit human-approval state.
4. Record a 90-second screen video and write a one-page scope/checklist. Show the before/after process and a failed/low-confidence case.

**Learning cap:** 8–10 focused hours. Learn structured output, API error handling, prompt testing, and webhook/API integration only as required by the demo.

### Week 2 — make it sellable and start conversations

**Outcome:** a proposal-ready offer and 25 targeted contacts/proposals.

1. Add the AI Workflow Pilot to your Upwork portfolio/profile as an adjacent service, retaining Django/Wagtail first in the headline.
2. Create three proposal snippets: lead handling, support/admin triage, and Django AI feature integration. Each should name the client’s bottleneck, a 5-day pilot, human review, and a discovery question.
3. Send 5 tightly matched Upwork proposals per weekday: Django/Python/API/automation jobs with an obvious business process. Do not chase generic “AI expert” posts.
4. Send 5 warm or direct messages per weekday to founders, agencies, former contacts, and local businesses with an existing workflow. Offer a 20-minute workflow triage, not free building.
5. Ask every conversation: “What is the repeated task, how many times per week, what happens when it goes wrong, and what system must receive the result?”

### Week 3 — ship one small proof asset and seek paid discovery

**Outcome:** 3 discovery conversations and one paid-pilot proposal.

1. Turn the demo into a short case-study format: problem → workflow → review safeguard → result metric the client could measure.
2. Prepare a paid AI Workflow Blueprint: process map, risk notes, recommended pilot, scope, timeline, and fixed-price estimate. Price at $250; credit it toward a build over $1,000.
3. Continue daily proposal/outreach rhythm. Tailor the demo only when the prospect’s workflow is materially similar.
4. For existing Django/Wagtail prospects, use this cross-sell question: “Which recurring content, lead, or support task currently makes someone copy information between systems?”

### Week 4 — convert or refine based on evidence

**Outcome:** one paid pilot, or a precise diagnosis of the objection blocking it.

1. Follow up every active conversation twice with a concrete workflow observation and a small next step.
2. If a pilot closes, deliver it with a kickoff checklist, acceptance criteria, weekly update, and handover video.
3. If none closes after 100 targeted touches/proposals, inspect your data: role targeted, bottleneck named, response rate, calls, proposals, and objections. Change **one** variable—vertical, offer wording, or proof asset—not the whole direction.
4. Collect a testimonial that names the business process, speed, reliability, and communication; do not ask for vague praise.

## Days 31–60: add RAG carefully and raise deal value

### Week 5 — build the knowledge-search foundation

**Outcome:** a secure, evaluable RAG demo in Django.

1. Build for a narrow source set such as employee policies or product manuals—not mixed web content.
2. Implement: document upload, text extraction, chunking, embeddings/vector search, answer generation, source citations, and delete/re-index capability.
3. Add basic authentication and restrict users to one demo organization. Never put client documents into a public demo.
4. Create 20 questions: 12 answerable, 4 ambiguous, 4 unanswerable. Record expected source and acceptable answer behavior.

**Learning cap:** 10–12 hours. Do not study every vector database or framework. Choose one simple stack compatible with your Django deployment and finish it.

### Week 6 — sell the RAG pilot to the right buyers

**Outcome:** 20 targeted RAG contacts/proposals and 2 discovery calls.

Target only businesses that have repeated questions and a controlled corpus: agencies, operations-heavy service firms, B2B SaaS teams, training providers, or teams with internal policies. Avoid prospects asking for “ChatGPT trained on the internet.”

Use this qualification gate:

- At least 20 recurring staff/customer questions per month
- A responsible person can supply and approve source documents
- Answers can be limited to an agreed document set
- A staff owner will test 20 questions before launch

### Weeks 7–8 — deliver, document, productize

**Outcome:** a $1,200–2,500 pilot or reusable assets that shorten the next sale.

1. Run the 20-question evaluation before and after changes. Log failures by category: retrieval, source quality, ambiguous question, refusal, or answer quality.
2. Create standard templates: data/source checklist, evaluation sheet, deployment checklist, and handover guide.
3. Add the winning automation or RAG proof to proposals and portfolio. Use real client results only with permission; otherwise use a clearly labelled demo.
4. Offer the previous client a small support retainer only if there is ongoing source refresh, monitoring, or workflow improvement. Do not force retainers onto a completed fixed-scope job.

## Days 61–90: become a focused implementation consultant

### Weeks 9–10 — sell paid blueprints and implementation bundles

**Outcome:** a repeatable consult-to-build path.

1. Run AI Workflow Blueprints for qualified leads. Limit each to one core workflow and deliver a decision within 48 hours.
2. Offer one of three next steps: Workflow Pilot ($750), Knowledge Search Pilot ($1,500), or a custom Django/Wagtail implementation with the AI component as a scoped module.
3. Package a Wagtail add-on only after a relevant request: “AI content drafting and review workflow” with editor approval, prompt versioning, and no automatic publishing.
4. Publish one short practical post per week drawn from real work: a before/after workflow, a RAG evaluation lesson, or a safeguard that prevented a bad automation. End with the pilot offer.

### Week 11 — learn MCP only through a concrete integration

**Outcome:** a minimal, safe MCP proof of capability—not a new service category.

1. Build or integrate one read-only MCP tool around a system you know (for example, search approved Wagtail content or retrieve a customer record summary).
2. Require authentication, narrow inputs/outputs, audit logging, and no write action by default.
3. Position it as an optional implementation detail in technical conversations: “I can securely expose selected internal actions to approved AI tools.” Do not lead with MCP jargon in outreach.

**Learning cap:** 6 hours unless a paid client requires more.

### Week 12 — decide the next 90 days from revenue data

Track by offer: targeted contacts/proposals, replies, calls, paid blueprints, pilots sold, revenue, delivery hours, and follow-on opportunities.

- Double down on the offer with the best combination of close rate, margin, and credible demand.
- Keep the Wagtail Sprint primary if it generates faster/better opportunities; sell GenAI as its value-adding module.
- If automation wins, specialize in one workflow family (lead operations, content operations, or internal support) rather than adding more AI technologies.
- Only consider fine-tuning/distillation after a paying client has a high-volume, stable task; 100+ high-quality examples; a measurable baseline; and a budget that beats prompt/RAG costs.

## Minimum technical bar before accepting paid GenAI work

Use this as a pre-flight checklist:

- API keys remain server-side and out of logs/repositories.
- Inputs and outputs are validated; structured output has a fallback path.
- A person reviews anything customer-facing, financial, legal, medical, irreversible, or low-confidence.
- You set spending/rate limits and can identify which requests used tokens.
- Client data retention, access, source ownership, and deletion are agreed in writing.
- You have acceptance tests based on real examples, including failure and no-answer cases.
- The scope names exclusions, support window, and change-control process.

## Weekly scorecard

Track this every Friday in one page. It prevents learning from becoming avoidance.

| Metric | Weekly target for days 1–30 | Weekly target for days 31–90 |
| --- | ---: | ---: |
| Matched Upwork proposals | 25 | 20 |
| Direct/warm outreach messages | 25 | 20 |
| Follow-ups | 15 | 15 |
| Discovery calls booked | 2 | 2 |
| Paid blueprint/pilot proposals sent | 1 | 1 |
| New reusable proof asset | 1 per month | 1 per month |
| Learning/building hours | 8–10 | 6–10 |

## 90-day success definition

This plan is working if, by day 90, you have:

1. Maintained active Django/Wagtail selling rather than waiting for an AI credential.
2. Shipped one automation and one RAG proof asset with clear scope and safeguards.
3. Held at least 8 qualified discovery conversations.
4. Sold at least one paid AI workflow/RAG blueprint or pilot, ideally alongside Django/Wagtail work.
5. Chosen one narrow AI implementation lane based on actual response and revenue data.

The priority is cash-producing, reliable implementation. Depth in distillation, fine-tuning, autonomous agents, and tool-specific platforms can come later—once a client’s repeated, paid problem justifies it.
