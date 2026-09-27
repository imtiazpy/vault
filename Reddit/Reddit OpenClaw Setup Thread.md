# My Openclaw Setup - AMA

**Community:** r/openclaw · **Posted by:** u/newbie2coding · **Score:** 6 upvotes · **Date:** July 11, 2026

**Source:** https://www.reddit.com/r/openclaw/comments/1ut5bki/my_openclaw_setup_ama/

---

I’ve been working on my OpenClaw setup for the past few months, and I’ve been excited to finally share it with the community.  
It’s come a long way since I first started, and I’ve learned a ton through trial and error, testing different ideas, and slowly refining my setup. There are still plenty of things I’m working on, but I’m really happy with how it’s coming together.  
I thought it’d be fun to do an **AMA (Ask Me Anything)!**  
Whether you’re curious about my hardware, the models I’m using, how I have things configured, my workflow, lessons I’ve learned, or anything else OpenClaw-related, ask away. I’m happy to answer questions, share what’s worked (and what hasn’t), and hopefully help anyone who’s building their own setup.  
I’d also love to hear what everyone else is working on. This community has been a great source of ideas and inspiration, and I’m always interested in seeing different approaches.  
Looking forward to the questions!

---

## Comments (7 fetched)

---

**u/BangCrash** · 1 points · Jul 11, 2026

What's your main use case for it?

How are you managing memory?

What did you do for soul.md and agents.md?


---

> **u/newbie2coding** · 2 points

> Right now the biggest focus is helping run my business. I’m a videographer, so I’m building around real problems I deal with every day instead of just experimenting for the sake of it.  
> For memory, I’m using persistent project documentation, structured state, and retrieving only the information that’s actually relevant to the task instead of trying to cram everything into context. That’s still an area I’m constantly improving because I think it’s one of the hardest problems to solve well.  
> I also rewrote both soul.md and agents.md quite a bit. I wanted each agent to have a clearly defined role instead of every agent trying to do everything. On top of that, I built a governance layer with review paths, approval gates, and fail-closed behavior so the agents work together more like a real team than a group of independent assistants. That’s honestly been one of the more interesting parts of the project for me.

**u/heythiswayup** · 1 points · Jul 11, 2026

Which local  llm are you using?  
As you’re a videographer (also my line of work) have you looked into integrating agents into your video editing workflow? For my own I’ve been looking into making rough cuts and assemblies from talking heads and premiere pro

---

> **u/newbie2coding** · 1 points

> Right now my local workhorse is **Qwen3 36B A3B** for orchestration and a lot of the day-to-day tasks. Then I’ll route to cloud models when something benefits from stronger reasoning or coding.  
> And yeah, I’ve definitely been thinking about the editing side. Right now I’ve been focused more on the business operations around editing, client emails, scheduling, research, documentation, coding, etc., because that’s what eats up the most time.  
> But one of my long-term goals is actually building an AI editor. There are AI montage editors and podcast editors everywhere now, but I haven’t found anything that can actually edit story-driven content the way a human editor does. It can cut silence or make a highlight reel, but it doesn’t understand pacing, emotion, callbacks, or how to build a narrative.  
> That’s what got me interested in building one myself. I don’t see AI replacing editors, I see it becoming another tool. If I can get it to build a solid first pass of a documentary or interview-driven piece, then I can spend my time making creative decisions instead of doing the repetitive assembly work. I think that’s where the real value is.

**u/Sufficient_Dig207** · 1 points · Jul 11, 2026

Does it have a chat interface where we can just ask your openclaw instead of you? 

---

**u/Sufficient_Dig207** · 1 points · Jul 11, 2026

What functions do you like about openclaw? Why do you choose Openclaw instead of a coding agent? 

---

> **u/newbie2coding** · 1 points

> Honestly, I like how open-ended OpenClaw is. It’s not locked into one purpose.  
> A coding agent is great if all you want to do is code. I wanted something that could handle coding, research, automation, and whatever else I decide to build next.  
> The biggest reason I chose OpenClaw is because I can shape it into exactly what I need instead of trying to fit my workflow into someone else’s product. That’s what keeps me coming back to it.

> > **u/Sufficient_Dig207** · 1 points

> > That's definitely a big misunderstanding. Coding agent can do way more than coding. 
> > 
> > I work in a big corporate so don't have the option to use openclaw. But I can build a whole personal assistant like openclaw using coding agent + tool connections + skills.

> > > **u/newbie2coding** · 2 points

> > > That’s a good point, and I probably oversimplified it. I know coding agents can do way more than just code now. I guess what I was trying to say is that I enjoy having a framework where I can define my own architecture, agents, workflows, and integrations instead of building everything around a single coding agent. It’s more about how I like to build than what the tools are capable of.  
> > > At the end of the day, if someone can build the same thing with Claude Code or Codex, that’s awesome. There are a lot of ways to get to the same destination.

**u/Houssein_** · 1 points · Jul 11, 2026

did it make you any money or not at all? if ir did do u mind sharing how , and also other ways to make money with it. thank you.

---

> **u/newbie2coding** · 2 points

> Not directly, at least not yet.  
> For me it’s more about saving time than generating revenue by itself. I’m building it to automate parts of my business that normally take hours every week like client communication, scheduling, research, documentation, and eventually parts of my editing workflow.  
> The goal is that I can spend more time on work that actually makes money instead of administrative tasks.  
> I also think there are plenty of ways people could make money with OpenClaw like building automations for businesses, creating custom AI workflows for clients, or using it to streamline their own business. That’s probably where I see the biggest opportunity.

**u/buffalosolja42** · 1 points · Jul 11, 2026

I think I over engineered mine and I review all local llms and test with Hermes.  I run a DGX spark and about to add another.  I feel earlier versions of Openclaw worked easier or better to work with.  But honestly I have stepped away from it and will revisit as soon as I am done with coding projects. I like your idea i think my problem is I got to rigorous looking at others Csuite stuff I locked it down with too much logic.  I look your approach. 

---

> **u/newbie2coding** · 1 points

> I know exactly what you mean. I caught myself doing the same thing early on. 😅  
> At one point I was adding logic for every possible scenario, and it actually made the system harder to work with. Lately I’ve been trying to keep the architecture solid but let the models do more of the heavy lifting.  
> I think there’s definitely a balance. Too little structure and things get messy. Too much and you end up fighting your own system instead of using it.  
> I’d be interested to hear what you think when you dive back into it. Always cool to compare notes with someone who’s gone down the same rabbit hole.

**u/Haunting-Machine7946** · 1 points · Jul 11, 2026

How do you run it? Is it on an isolated Mac mini? What models do you use?  What are five actual use cases that are actually helpful to be run by open claw instead of you doing it yourself? I’ve seen lots of ai slop out but those are things that I feel even if you don’t have a openclaw it’s fine. it’s something mundane then you can actually do it yourself. It’s not real life changing offloading kind of activity

---

> **u/newbie2coding** · 3 points

> Yep, it’s running on a dedicated headless Mac mini in my homelab. I use a mix of local and cloud models depending on what the task needs.  
> As for actual use cases, here’s where it’s been useful for me:  
> My client email workflow. It’ll classify incoming emails, check my calendar, draft responses, and get everything ready for approval instead of me doing it all manually.  
> Software development. I’ve got different agents handling planning, coding, reviews, and architecture. It’s made working on larger projects a lot more organized.  
> Research. Instead of me spending hours digging through docs and articles, I can have it gather information, compare options, and give me something useful to work from.  
> Documentation. It helps keep long-running projects organized so I’m not constantly trying to remember why I made a decision three months ago.  
> General business tasks. Anything repetitive that doesn’t really need me personally doing it.  
> I get what you’re saying though. There’s definitely a lot of AI projects that are basically demos. I wasn’t interested in building another chatbot. I’ve spent most of my time on the architecture underneath it and making it reliable enough that I can actually trust it to help run parts of my business. That’s been the fun part for me.

> > **u/cyanexttue** · 1 points

> > pls explain in detail your agents team setup and structure.
> > 
> > what skills do you use for the teamlead agent etc

> > > **u/newbie2coding** · 1 points

> > > It’s honestly evolved a lot over the last few months, but the basic idea is pretty simple.  
> > > I have one lead agent (Tom) that acts like a project manager. It figures out what the task actually is, decides which agent should handle it, and keeps track of the overall workflow.  
> > > From there I have specialized agents. Spike is focused on engineering and implementation, Athena is responsible for architecture and governance reviews, Goose handles research and gathering information. Each one has a clearly defined job instead of trying to make every agent good at everything.  
> > > I also spent a lot of time building the governance around them. There are approval gates, review paths, defined responsibilities, and fail-closed behavior so agents can’t just go off and make changes without oversight.  
> > > It’s less “here are four chatbots” and more trying to make them operate like a small engineering team.

> > **u/pmarsh** · 1 points

> > This is probably just a question for AI but how do you say what models to use per task?
> > 
> > What have you found works well local versus cloud?

> > > **u/newbie2coding** · 2 points

> > > I don’t hardcode one model for everything. I try to match the model to the task.  
> > > If something is straightforward, fast, or happens a lot, I’ll use a local model because it’s basically free to run, low latency, and keeps everything private.  
> > > If I need deep reasoning, complex coding, architecture decisions, or something where quality matters more than speed or cost, I’ll route it to a cloud model.  
> > > I think local vs. cloud isn’t really an either/or anymore. They complement each other really well. The trick is building a system that knows when each one makes sense instead of always defaulting to the biggest model available. That’s actually been one of the more fun parts of the project.