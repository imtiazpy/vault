# Where is OpenClaw heading? Curious how people are using it in real projects

**Community:** r/openclaw · **Posted by:** u/imtiaz_py · **Score:** 23 upvotes · **Date:** July 10, 2026

**Source:** https://www.reddit.com/r/openclaw/comments/1usnren/where_is_openclaw_heading_curious_how_people_are/

---

Hi everyone,

I'm a full-stack developer currently diving deeper into AI engineering. Over the past few months I've been learning about LLMs, AI agents, MCP, workflow automation, and the broader AI ecosystem.

I've been following **OpenClaw** for the past couple of months, though I haven't had the chance to build with it yet. Now I'm curious to see how the project has evolved and what kinds of real-world applications people are building with it., it's a bit difficult to gauge how people are actually using it beyond demos and tutorials.

I'd love to hear from those who have been experimenting with it.

Some questions I'm curious about:

* What are you building with OpenClaw?
* What kinds of problems is it particularly good at solving?
* Have you deployed anything to production, or is it mostly experimental at this stage?
* How does it compare with other agent frameworks or automation tools you've used?
* If someone wanted to become proficient with OpenClaw today, what would you recommend they focus on?

I'm not looking for a quick "is it worth it?" answer. I'm more interested in understanding where the project is heading, what the community is building, and where you see the biggest opportunities over the next year or two.

Looking forward to learning from everyone's experiences. Thanks!

---

## Comments (18 fetched)

---

**u/GeekTX** · 7 points · Jul 10, 2026

I use OC daily and it has full and unencumbered access to not just my pc but to my lab that has a 4 node Proxmox cluster, 3 GPUs, 1 mid-capacity (\~30TB) NAS and another higher capacity (\~70TB) NAS. At this point about 75% of my work is OC based. Most of my routine tasks are being automated and adopted into the environment daily. I use n8n for all deterministic automations and when there isn’t an automation/workflow already available … I have OC build a new workflow, test and prove it, then deploy to my production instance. 

---

> **u/imtiaz_py** · 3 points

> Sounds interesting. Haven't reached that level yet. Trying to get my around all of these (The AI paradigm shift)

> **u/tekneeque** · 3 points

> Do you even need n8n when Claude can just script it?

> > **u/GeekTX** · 4 points

> > I don't use Claude and I really love n8n ... it gives me canvas to iterate over the automation with my agent for ... but there are a bunch of automations that I create that are for my clients and I use n8n for them as well. 

> > > **u/tekneeque** · 2 points

> > > Ah... that makes sense. n8n is an automation beast.
> > > 
> > > 

> > **u/xaijin** · 2 points

> > N8n is good for repeatable processes that you need to inject an agent into to. They're complementary.

**u/Gipity-Steve** · 5 points · Jul 11, 2026

I've read all 32 replies in this post so far. And what I'm getting is "not very much". I think there is huge opportunity for tools like OpenClaw. but so far, after nearly 6 months out in the wild, it sounds like people are still trying to figure out the life-altering "why" for OC.

---

> **u/Tillinah** · 4 points

> I think when you could use your claude subscription with it, it was more enticing. But having to use alternative, lesser capable models or API tokens instead just isn't as fun. 

> > **u/Gipity-Steve** · 5 points

> > Get used to it. VCs won't fund AI model providers forever. Subscriptions are only there to entice us all in. Token usage based will be the future.

> > > **u/DragSweet7501** · 2 points

> > > Totally agree. Hopefully costs for reasonably capable models will go down and moderate use stays at the Netflix-subscription level. 

> **u/imtiaz_py** · 3 points

> Yeah, that's the impression I'm getting as well. I'm still trying to figure out the real-world use cases. Have you built anything substantial with OpenClaw? I'd love to hear what you've been using it for.

> > **u/Gipity-Steve** · 1 points

> > Not really, just experimental stuff - email management and all the usual stuff everyone is trying. Still trying to find the golden use case that makes it worth while.

**u/nz365guy** · 5 points · Jul 11, 2026

I have 26 Agents in my setup. I have it hosted on Azure, running on Ubuntu.

I have a 10-agent DevOps team. Each agent in this team stays in their lane and performs their role as part of a full DevOps team. The security agent in this team also has a range of Red Team tools to test all code written. I have created a range of business tools with this team.  
URL shortener  
5 websites with a customer-built commenting tool, subscriber tool and social sharing tool  
I have built an SEO and LLMO tool integrated with Google Analytics and Google Search each Monday it updates itself from various sources and then tweaks my sites accordingly.  
I have built a Business Operating Systems with 11 departments each with its own agent that own the capability. This sales, marketing, legal, hr etc.

I have built a heap of other stuff and learned a lot about AI. Including building my own model router with 9 LLM providers, cost optimisation, memory, RAG, loops and a heap of other stuff.

No way I am going to be locked into a single LLM provider.

---

> **u/mrtimbuktwo** · 5 points

> Are you turnung a profit?

> > **u/nz365guy** · 2 points

> > Yes

> **u/imtiaz_py** · 1 points

> That's a seriously impressive setup. I like how you've structured it around specialized agents rather than trying to have one agent handle everything. It sounds like you've gone well beyond experimentation.
> 
> If you don't mind me asking, what kind of work do you do? Are these systems mostly for your own business, or are you building and deploying them for clients as well? I'm also curious, what are clients actually looking for these days when it comes to automation, AI agents, or AI engineering in general?
> 
> And one more thing: with a setup like this, are you able to monetize it, or is it primarily an internal productivity investment? Also, when starting a new project, how do you decide whether OpenClaw is the right tool versus using something else?

> **u/imtiaz_py** · 1 points

> Out of curiosity, are you mainly using it for your own workflows, or have you also built solutions for clients or businesses?
> 
> I came across a few discussions mentioning that, since OpenClaw operates with full system access and persistent credentials, it's generally not recommended to run it on personal workstations or devices with sensitive data. Has that influenced how you deploy or use it?

> > **u/smuckola** · 2 points

> > That's all gibberish. It's software so it runs how you configure it. If a person can't assess secure dangerous software, and that isn't their absolute priority, they shouldnt be using it. You dont install internet servers on your naked workstation; that's insanely unnecessary. My system runs on Fedora Linux in a systemd container. On macOS, you put it in an alclss account. I had AI guide me on configuring it.
> > 
> > edit: and i DARN sure don't let openclaw handle its own conf files! I set them read-only and immutable because that conniving thing will hijack write permissions if it can. I constantly asked its guidance on security and ran "openclaw doctor".

> > > **u/imtiaz_py** · 1 points

> > > Ah I see! Interesting take. Looks like I might wanna try it out.  

**u/elgafas** · 5 points · Jul 11, 2026

https://preview.redd.it/r4nvy6zcqmch1.png?width=1811&format=png&auto=webp&s=37340458aedbe878e6deea4dab0417872f9c50af

I'm using OpenClaw for L&D. 14 agents across two Beelink SER9 mini PCs, each handling pieces of the process and I built a simple “mission control” to keep it all moving. It's an ADDIE-style flow with checkpoints, and I review the work between stages and provide feedback and new inputs. Also has a LLM-Wiki ingestion system that I use to ground and align the inputs and outputs. It’s still evolving, but I'm already using it for real work, not demos.

I don’t think one agent framework or orchestrator is automatically better than another. Claude Code, OpenClaw, whatever, it really depends on the use case, the tools you need it to call, how clear the instructions are, and how much useful context you give it. I can see why the differences matter more for coding workflows, but for L&D I haven’t really run into any major problems with OpenClaw.

---

> **u/imtiaz_py** · 1 points

> Interesting! I agree with the point that no agent framework or orchestrator is better than another. It's actually the use case that matters - you can use whatever tools you feel comfortable with.   
> By the way could you please share how you built a 'mission control' and connect the 14 agents? What are these 14 agents doing? 

**u/thatkidgobe** · 3 points · Jul 10, 2026

Building a SaaS with Claude Code (Opus). Trying to get Claude to teach my OC how to be my marketing agent. Feel like OC is his dumb little brother because he’s only on GPT-5.4-mini. We’ll see how it continues to go lol. 

---

> **u/RawFreakCalm** · 3 points

> Just get Kimi claw or use a different model. 5.4 mini will just feel dumb. Even qwen 3.6 would be better. 

> > **u/thatkidgobe** · 1 points

> > I’ll look into those. Thanks!

> > **u/imtiaz_py** · 1 points

> > Isn't Kimi claw still a beta version? Is it suitable for production level SaaS?

> > > **u/RawFreakCalm** · 2 points

> > > Probably depends on the use case but I’ve found it stable. 

> > > > **u/imtiaz_py** · 1 points

> > > > What type of projects/workflow automations have you built so far with Kimi? and in general what type of automations do you do with tools like n8n, OC, kimi etc?

> > > > > **u/RawFreakCalm** · 2 points

> > > > > I run a marketing agency and a consulting firm. 
> > > > > 
> > > > > Every morning I have a bot pull all messages from telegram, slack, emails, and meeting notes and compile a list of to do tasks. It then lists what tasks ai can do and what I need to do and we divide the work. 
> > > > > 
> > > > > I also have a bot that checks my email every hour and highlights what needs a response. 
> > > > > 
> > > > > And one that codes new api configurations dashboards. Another to create presentations, another for my promotion campaigns. 
> > > > > 
> > > > > I still need humans in the work. But I probably get about 8x output or so of where I would be without ai. 

> > > > > > **u/imtiaz_py** · 1 points

> > > > > > That's a really practical way of using AI. What stood out to me is that you're not trying to replace yourself, you've delegated the repetitive and time-consuming work while keeping the decisions that still need human judgment.
> > > > > > 
> > > > > > I recently came across the **4D Framework for AI Fluency** (Delegate, Describe, Discern, Diligence), and your setup seems to fit the *Delegate* part almost perfectly.
> > > > > > 
> > > > > > Since I'm still making the transition into AI engineering, do you have any advice on where to start if the goal is to build these kinds of systems for clients? Are there a few automation use cases that consistently deliver value across different businesses, or does it vary a lot depending on the client?

> > > > > > > **u/RawFreakCalm** · 1 points

> > > > > > > Varies a lot, email is the most common. 
> > > > > > > 
> > > > > > > My advice is to just start building. I tried a few courses and found I learned much more taking action than reading.  

> **u/zfoong** · 1 points

> Curious, why not just use Claude? Is it because of the sustainability or the memory? 

> > **u/thatkidgobe** · 1 points

> > My desktop needs to be on for Claude to run a routine. So in the event it’s not on, it’s nice that my OC still runs (on my VPS) and I know the job will get done. (If there’s a better way please school me!)

> > **u/imtiaz_py** · 1 points

> > What type of workflow/automation have you done with Claude? Would you mind Schooling me when to chose one over other? like there are many tools n8n, openclaw, make(dot)com, Claude etc.

> **u/imtiaz_py** · 1 points

> Sounds interesting. What are you building, mind sharing?

**u/BP041** · 3 points · Jul 10, 2026

I've got ~18 Claude Code/OpenClaw cron jobs running on a Mac mini via launchd. Mostly content generation and lead scoring for my own SaaS. It's not a replacement for everything — tbh the quality still needs careful prompt engineering — but it's been solid for batch ops that I'd otherwise have to babysit.

---

> **u/imtiaz_py** · 1 points

> Thanks for sharing! Could you elaborate a bit on why you run them as cron jobs? Is it because the tasks are scheduled by nature, or is there another advantage I'm missing?

> > **u/BP041** · 3 points

> > Yeah, mostly they're scheduled by nature - daily reports and data syncs. But honestly, cron's just the simplest way to make sure they run reliably without babysitting.

> > > **u/imtiaz_py** · 1 points

> > > That makes sense. I guess reliability and simplicity are hard to beat for scheduled workloads.
> > > 
> > > Out of curiosity, have you found yourself using OpenClaw mainly for these periodic batch jobs, or do you also have use cases where it's event-driven or user-triggered? I'm trying to get a feel for where it fits best in real-world setups.

**u/ericgus** · 3 points · Jul 12, 2026

I used it as a hyper personalized head hunter to find a job and it found me a very very good one.. thats how I started using it, and on a raspberry Pi5 (that I had kicking around).. I have also used it to help me find a used car (as really its very much like job hunting) .. and now I am using it to manage my homeassistant and write its automations .. I am not using it for "for profit" uses .. I also occasionally use it for deep research into specific items of interest and to say monitor github projects for movement on bugs and such.. for what its worth I also setup a hermes agent just to see compare/contrast .. so far I like both, each has its unique features.

---

> **u/imtiaz_py** · 1 points

> That's a really interesting progression, from job hunting to Home Assistant and GitHub monitoring. The job search use case especially caught my attention.
> 
> If you don't mind sharing, how did you implement that workflow? Was OpenClaw actively searching and filtering opportunities based on your preferences, or was it more of an assistant helping you evaluate and prioritize jobs?
> 
> That part resonates with me because I'm currently looking for opportunities myself, so I'd be really interested to learn how you set it up and what role OpenClaw played in helping you land the job.

> > **u/ericgus** · 1 points

> > I had a number of API/MCP connections to job posting sources (like DICE and JSEARCH ), I gave it an expanded version of my resume in a more markdown machine distilled version (with help from Claude).. I told the bot to go out daily, check various job listings and find/score matches based on my resume and criteria, it would run a few times a day (mornings/evenings) , it also tracked which jobs it already notified me bout in a local sqlite db (I was going to use this for application tracking etc but didnt ever get that far ) , it would score the search results and email me its findings with links.. Searching for a car is similar you create a rubric for the type of car you want, price and distance you are willing to drive , find matches, score them, email them .. for home assistant I have it hooked into HA and it can also sftp/ssh in and modify the automations or write new ones..

> > > **u/imtiaz_py** · 1 points

> > > Thanks for taking the time to explain it in detail. This is probably one of the most practical OpenClaw use cases I've come across.

**u/Chief1-1-7** · 2 points · Jul 11, 2026

Hi there,

For now iI'm trying to build a virtual assistant via telegram that allows me to drop him any info, and created some tasks to trigger. Example : Dropping a LinkedIn In post, to add as intel in a specific document that tracks some info a specific industry.

I have a small PC and looking into Spark from  Nvidia to run an open model locally, to create agents doing things such as OCR or other document reading / analysis.

For now, I have a bot that runs on Ubuntu via Windows, with NemoClaw to lock it out of my files. I don’t trust OC at all.

---

> **u/imtiaz_py** · 1 points

> That sounds like a practical use case. I like the idea of using Telegram as the interface, it seems much more natural than opening a web app every time.
> 
> I'm curious though, you mentioned you don't trust OpenClaw and are using NemoClaw to sandbox it. Is that mainly because of its system-level access, or have you run into specific issues that made you cautious? Also, are you planning to eventually use these agents for client work, or is this primarily for your own productivity?

**u/Particular_Beat_5447** · 2 points · Jul 11, 2026

I ran OpenClaw on my android Samsung S10 FE via Termux. Used a few models before such as GPT5.5, Opus 4.7, Kimi 2.7/Deepseek V4 Flash (via Ollama Cloud) before settling to GLM5.2.

My STT were using Groq Whisper, TTS on Elevenlabs (all free tiers). So I can send voice notes when I’m driving, and OC can reply me with voice too. 

I use OC for daily light tasks such as briefings, mail summary, appointments booking, create invoices, etc. This is as practical as how a non-tech person would use it. Honestly speaking, you might not need OC much if you don’t have any real task in mind, but if you just want to experiment what it can do then you can hop in and try it out.

---

> **u/imtiaz_py** · 1 points

> That's a pretty cool setup, especially running it from your phone. I hadn't considered using OpenClaw that way.
> 
> I'm curious how did you get OpenClaw running on your Samsung via Termux? Has it been stable and practical enough for day-to-day use, or does it feel a bit constrained on mobile?
> 
> Also, you mentioned settling on GLM 5.2. Do you use that for everything, or do you have some kind of model router that picks different LLMs depending on the task? I'd be interested to hear how you decided on that setup.

**u/TheRealAndyML** · 2 points · Jul 12, 2026

For me the magic is in feeding OpenClaw api docs, and setting it loose on another system. It’ll write scripts (or build n8n workflows if you want, directly via the api), and can juggle data from multiple sources for powerful automations and reports quickly and easily. It can even integrate with some systems that don’t have APIs, either by hacking their file based backends or using screen grabs and computer use automations. 

My advice would be to stop sleeping on local agents and get to work tinkering. You’ll answer your own questions quickly by using it. 

---

> **u/imtiaz_py** · 1 points

> Thanks for the advice. You're probably right, at some point I need to stop reading about all these tools and start building with them.

**u/TowerStandard3868** · 2 points · Jul 17, 2026

I run OC in a docker container in a VM on a separate machine on a separate VLAN.  
My only access is from my local desktop

It's like an enthusiastic intern who is never going to get access to my email!  
Do I trust it? hell no!

One rainy weekend it setup a information system that would taken a week to build even using claude code.

I have deepseek 7B and qwen-instruct running in a separate container with an 8GB GPU and ollama running nomic-embed-text on a nvidia xavier (ancient but usable)

I got OC to setup folders broken up into sub categories in which I drop documents via an  NFS mount to be summarized (exported from the VM). The summary and the doc go into lancedb ( a vector db)  
  
All queries for the local documents stay local.  
I uploaded a diesel engine manual and now can just ask what oil or where is the anode .....   
Including 'from local' or 'from lance' or 'use lance' in a query and it goes via the local deepseek LLM 

Because each category has different items of interest it has setup the ability to set custom prompts for qwen-instruct to use when creating the summaries. It recommend qwen-instruct for the summaries

I switch between Claude and deepseek online for the non local queries.  
Deepseek is far cheaper  


It uses perplexity for web search  
I have got it to provide me daily news summaries on various topics sent via telegram  
It has watch lists that only report if new details emerge  
It has automatically created once off triggers to search on a particular date that it identified as a up coming announcement for a news article (results of a shareholder vote)  
It created a task dashboard to provide an over view of the various watch lists  


It suggested and then setup the embedding to fail over back to the local machine if the Xavier is down  
It also provided me metrics to compare using the local machine versus the xavier.  
using the Xavier frees up some vram

It cost a lot of tokens to get it to build this, though in reality it worked out only about $10 ph using claude.  
  
It implemented all this on a rainy weekend, just by asking it to do it. Well actually more  along the lines I want to ... and it presented the options.   
All I had to do was when requested add a couple of lines to the docker file and run the occasional docker compose command.

It has automatically created a todo list of items I need to attend to on my boat, based on a survey I dropped in the boat folder. It then added to the do list from general conversations. It has picked up various items I need to clarify to help answer questions I had. like what model is this part you need to service, and has added a tasks like get model number of item x, or measure the genoa track

I asked about a self improvement tool in the OC tool repo  
It responded hey I can do this and wrote it's own  
Now it asks should I save this skill or remember not to do ..

Even without all of the above simply keeping context across LLM providers is awesome. If Anthropic put their price up there is no resistance to prevent me changing providers because my chat context/history is local 

Next addition is using colibri on a separate VM to do local inference on local documents in a batch mode using a local  but slow frontier model. (GLM-5.2-colibri-int4) 

If you install OC on the same bare metal machine as your data and email, then you are insane! It has recognized my isolation bent and includes consideration of this in it's responses, along the lines of "You could do this but as you want isolation you should do this."

I'd say the barrier to entry is knowing how to install OC securely in it's own sandpit and knowing to say no when it asks for your email credentials, 'so it can send you email'.  


---

> **u/imtiaz_py** · 1 points

> Thanks for taking the time to write all of this. This is probably one of the most insightful real-world OpenClaw setups I've read so far.
> 
> A few things really stood out to me. First, your security-first approach. Treating it as "an enthusiastic intern" with strict boundaries makes a lot of sense. Second, I hadn't even thought about keeping the chat history and context local so switching between LLM providers becomes almost frictionless. That's a huge advantage.
> 
> I also found it fascinating that it built most of the infrastructure itself just from high-level goals. That's the part I'm trying to wrap my head around as I explore agentic workflows.
> 
> Out of curiosity, what does your background look like? Are you a software engineer by profession, or did you gradually learn Docker, networking, self-hosting, and all these pieces because of OpenClaw? Your setup feels like the result of a lot of experience, and it's genuinely inspiring to see what's possible.
> 
> And thanks for the final advice. I think "install it securely in its own sandpit and don't hand over your email credentials" is something every newcomer should hear.

**u/dresden_k** · 2 points · Jul 19, 2026

The cool thing is how you can build all kinds of things on it. It's the PC ecosystem, figuratively speaking. 

Problems solved - customizable in a way that Claude Code/Cowork and Codex don't allow. I have a 7 part memory stack for mine that it built. Custom everything. If you have an imagination and some problems to solve, it solves them better than Claude Code or Cowork can. 

If you just need a model to help you do basic AI stuff it's the wrong tool. If you need something to help you code, just use Codex or Claude Code. If you want something to go through your email, use Claude Cowork. 

A friend of mine, with my help, owns a coffee roasting company, and we're building a system with physical sensors, cameras, and other inputs, to monitor a large coffee roasting operation to help the human coffee roaster do their job better, with more information points. We're using the OpenClaw agent to help create a non-AI, with AI Oversight, software system to do as much coffee roasting oversight as possible to help the human coffee roaster get the most out of each batch, as close to perfect as possible. 

"Is it worth it" can only be answered by "what is the problem you're trying to solve."

---

> **u/imtiaz_py** · 1 points

> That's a great insight. I really like your point that the value depends on the problem you're trying to solve, not the tool itself.
> 
> The coffee roasting project sounds especially interesting. I'd genuinely love to follow its progress if you're open to sharing updates along the way. It's exactly these kinds of real-world implementations that help people like me better understand where agentic systems create actual business value.

**u/tallymebanana72** · 1 points · Jul 11, 2026

I've setup a family assistant in Whatapp. I've got it setup state my location if asked. I've also given it a google calendar where it can keep track of events and give a daily update on what's on, inc. weather. I've now added where it will make outbound phone calls and report back what was answered on the call. I'm mainly just playing around with it to try to understand how it can be secured.  

---

> **u/imtiaz_py** · 2 points

> Sounds interesting about the Family assistant. Where have you deployed it, how much does it cost you to run it?

> > **u/tallymebanana72** · 2 points

> > It has been very interesting. It’s running on an Ubuntu VM on an old Mac. I’m using Grok under a €35 3-month offer for most of it, and OpenAI only for the voice-call side, which has just cost a few euro so far. Twilio is separate for the phone number and call costs.

> > > **u/imtiaz_py** · 1 points

> > > Are you planning to use it for personal use cases only? By the way what industry are you in? Providing any automation services to clients?

> > > > **u/tallymebanana72** · 1 points

> > > > For now it’s mainly a personal project and a way of learning what these agents can safely automate. I work in banking information security, particularly grc, so the security side interests me as much as the automation. **I’ve** no plans to offer **any services** at the moment.

> > > > > **u/imtiaz_py** · 1 points

> > > > > Thanks for sharing your experience, it was really helpful. Wishing you the best with the project, and I'd be interested to hear how it evolves over time.

**u/namanyayg** · 1 points · Jul 12, 2026

I'd judge it by the boundary around the agent, not the agent itself.

For production-ish work, the setup that seems sane is:

- run it in a separate machine/container with only the accounts/files it needs
- make it write a plan or diff before touching anything risky
- keep an action log so you can replay what happened
- put hard stops around customer-facing sends, payments, deletes, credentials

The use case I'd trust most is scheduled/batch work where a bad output is visible before it escapes: daily summaries, lead scoring, pulling docs into a knowledge base, checking a repo for changes, that kind of thing.

The scary version is "full desktop access plus persistent credentials plus no audit trail." That can look magical right up until it quietly does the wrong thing.

---

> **u/imtiaz_py** · 1 points

> Thanks, this is a really practical way to think about it. I like your point about judging the boundary around the agent rather than the agent itself. 
> 
> Your examples also make sense. Starting with scheduled or batch workflows where the output can be reviewed feels like a much safer way to build confidence before giving an agent more responsibility.
> 
> Out of curiosity, are you following these principles from your own production experience, or are they more general best practices you've picked up? I'd also be interested to know what the most advanced workflow you've trusted an agent with so far has been.

**u/Rohit_Aarvion** · 1 points · Jul 17, 2026

these are my thoughts 1. open claw needs a far easier onboarding process make it usable for wider audience, currently its a tech only product you need to invest serious time to deploy it. Make it as simple as a any b2c app see it explod in usage.2 how do i chain my claw?? give me a solution to block what its trying to do so that my anxiety levels do not peak :).(full disclosure: have launched a product for this)

---

> **u/imtiaz_py** · 1 points

> Could you please a bit more about the product that you mentioned?

**u/Civil-Ad5290** · 1 points · Jul 10, 2026

it seems invasive but super useful, isn't it?



---

> **u/imtiaz_py** · 1 points

> Haven't used it yet. What's you opinion? Have you used it in your daily workflow? Are you serving clients with it?

> > **u/Civil-Ad5290** · 1 points

> > I researched a lot abt it on youtube, have used claude code instead ....
> > 
> > 

> > > **u/imtiaz_py** · 1 points

> > > I guess both are different than each other. Have you built any automation workflow with Claude code?

**u/Wonderful_Sample_590** · 0 points · Jul 11, 2026

after Claude banning oauth. I dont use OC anymore, not sure if others do the same

---

> **u/imtiaz_py** · 1 points

> What are your regular workflow automation tools?