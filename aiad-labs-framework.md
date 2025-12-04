# The AIAD Labs Framework

## Organizational Design for AI-Augmented Innovation Teams

---

## The Core Problem

Traditional R&D operates on assumptions that no longer hold:

1. **Building is expensive** → so we review before building
2. **Changing is costly** → so we plan extensively upfront
3. **Coordination is necessary** → so we have meetings, approvals, gates

AI-Augmented Development (AIAD) inverts these assumptions:

1. **Building is cheap** → build to think
2. **Changing is free** → iterate constantly
3. **Individuals can ship** → trust, don't coordinate

This requires a fundamentally different organizational model.

---

## The Two-Division Structure

```
                         ┌─────────────┐
                         │     CTO     │
                         └──────┬──────┘
                                │
              ┌─────────────────┴─────────────────┐
              │                                   │
    ┌─────────┴─────────┐           ┌─────────────┴─────────────┐
    │  LEGACY DIVISION  │           │          LABS             │
    │   (Sustaining)    │           │      (Innovation)         │
    └───────────────────┘           └───────────────────────────┘
```

### Legacy Division
- Traditional engineering structure
- Maintains existing products and infrastructure
- Follows established processes
- Reports through VP Engineering

### Labs Division
- AIAD-native innovation engine
- Ships experiments in 8-week cycles
- Zero legacy process
- Reports directly to CTO (protection from process creep)

**Why separate?** You cannot run AIAD inside a traditional org. The antibodies will kill it. Process creep, "consistency" requirements, resource borrowing during crunch—Labs must be black-boxed.

---

## The AIAD Pod Model

### The 3-Person Experiment Pod

Each experiment gets a single pod:

```
┌─────────────────────────────────────────────────────────────────┐
│                      EXPERIMENT POD                             │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐              │
│  │   BUILDER   │  │   BUILDER   │  │  AMPLIFIER  │              │
│  │             │  │             │  │             │              │
│  │ Full-stack  │  │ Full-stack  │  │ Community   │              │
│  │ + AI native │  │ + AI native │  │ + Content   │              │
│  │             │  │             │  │ + Testing   │              │
│  └─────────────┘  └─────────────┘  └─────────────┘              │
│        │                │                │                      │
│        └────────────────┼────────────────┘                      │
│                         │                                       │
│                  ┌──────┴──────┐                                │
│                  │  AI AGENTS  │                                │
│                  │ Claude Code │                                │
│                  │   Cursor    │                                │
│                  │  v0/Vercel  │                                │
│                  └─────────────┘                                │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### Role Definitions

#### Builder (2 per pod)

**What they are:** AIAD-native full-stack engineers

**Profile:**
- 3-7 years experience (enough to know good, not stuck in old ways)
- Demonstrable AIAD fluency—ship with Claude Code, Cursor as primary tools
- Comfortable as "orchestrator" of AI agents rather than typing every line
- Move between frontend, backend, and AI integration fluidly
- Bias toward action over perfection

**What they do:**
- Ship features daily using AI assistance
- Own entire vertical from idea to production
- Make technical decisions without committee
- Build in public (daily updates, demos)
- 80% building, 20% communicating

#### Amplifier (1 per pod)

**What they are:** Community builder + QA + content creator

**Profile:**
- Not necessarily technical (though technical literacy helps)
- Natural community builder—Discord native, content creator mindset
- Spot issues from user perspective
- Comfortable with public accountability

**What they do:**
- Manage community channels
- Create daily content (videos, posts, updates)
- First-line user testing and feedback collection
- Coordinate with Builders on priorities based on user signal
- Run beta programs
- 20% testing, 80% community/content

**Why this role matters:** Without it, Builders get pulled into community management and slow down.

### Platform Team (3-4 people)

Maintains shared infrastructure that enables pods to ship fast:

```
Platform Team
├── Platform Lead (1) - Architecture, standards, infrastructure
├── Platform Builder (1-2) - Shared services, tooling, AI integrations
└── DevOps/SRE (1) - Deployment, monitoring, cost management
```

**What they provide:**
- Shared AI integrations (LLM gateway, tool framework)
- Authentication/billing infrastructure
- Deployment pipelines
- Observability and monitoring

**What they DON'T do:**
- Review experiment code
- Approve experiment decisions
- Block experiment launches
- Impose process

They're enablers, not gatekeepers.

---

## Labs vs Legacy: The Differences

| Dimension | Legacy Division | Labs |
|-----------|-----------------|------|
| Team Size | 10-30 per team | 2-3 per pod |
| Shipping Cadence | Quarterly releases | Weekly/daily |
| Planning | Roadmaps, PRDs, reviews | 8-week experiments, fill or kill |
| Code Reviews | Multi-stage approval | AI-assisted, trust-based |
| Testing | Full QA cycles | Automated + user feedback |
| Tools | Established stack | Whatever ships fastest |
| AI Usage | Augmentation | Core methodology |
| Location | Office-based | Remote-first |

---

## The Black Box Principle

Labs operates with complete independence:

**No legacy processes:**
- No Jira (use simple task lists)
- No multi-week sprints (ship daily)
- No design reviews (ship and iterate)
- No code review committees (AI + peer trust)
- No roadmaps beyond 8 weeks

**No legacy dependencies:**
- Own infrastructure (not shared IT)
- Own tools (not enterprise-mandated)
- Own deployment (not release trains)
- Own decisions (not committee approval)

**Clean interfaces only:**
- Consume Legacy APIs when needed
- Provide APIs for Legacy consumption
- Never share codebases
- Never share process

### The Protection Mechanism

Labs reports directly to CTO, not through VP Engineering chain. This prevents:
- Legacy process creep
- "Consistency" requirements
- Resource borrowing during crunch
- Culture dilution

---

## The Interface Layer

### How Labs and Legacy Communicate

```
                    ┌──────────────────┐
                    │    INTERFACE     │
                    │    COMMITTEE     │
                    │  (meets weekly)  │
                    └────────┬─────────┘
                             │
        ┌────────────────────┼────────────────────┐
        │                    │                    │
        ▼                    ▼                    ▼
┌───────────────┐   ┌───────────────┐   ┌───────────────┐
│     LABS      │   │   API/SDK     │   │    LEGACY     │
│   Experiment  │◄──┤   Contract    │──►│    Teams      │
│     Pods      │   │               │   │               │
└───────────────┘   └───────────────┘   └───────────────┘
```

### Interface Committee (Weekly, 30 min)

**Attendees:**
- Labs Lead (represents all pods)
- Legacy Tech Lead (represents integration needs)
- CTO (tie-breaker, strategic alignment)

**Agenda:**
1. What Labs needs from Legacy (APIs, data, assets)
2. What Legacy needs from Labs (none, ideally)
3. Transition decisions (successful experiment → spinout?)

**Key principle:** Labs never waits on Legacy. If Labs needs something, they build a workaround. Interface Committee coordinates for efficiency, not permission.

---

## The Experiment Lifecycle

### 8-Week Fill or Kill

Every experiment gets 8 weeks. Launch or kill, no exceptions.

**Week 1-4: Idea to Private Beta**
- Week 1: Concept to clickable prototype
- Week 2-3: Core feature only (one AI-powered capability)
- Week 4: Private beta to 1,000 users, gather data

**Week 5-8: Private Beta to Public Launch**
- Week 5-6: Fix critical issues, add #1 requested feature
- Week 7: Submission/deployment preparation
- Week 8: Public launch OR kill decision

**Week 9+: Iterate at Speed (if launched)**
- Ship features weekly based on user data
- Fix bugs daily
- Major capability additions monthly

### Fill Criteria

All must be true to "fill" (continue):
- Week 8 metrics hit (25%+ D7 retention, 40%+ activation)
- Clear path to revenue
- User demand exceeds experiment capacity
- Product-market fit signals strong

### The Spinout Model

When an experiment succeeds, it graduates:

```
┌─────────────────────────────────────────────────────────────────────────┐
│                          EXPERIMENT LIFECYCLE                           │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                         │
│  LABS PHASE              SPINOUT PHASE              MATURE PHASE        │
│  (8 weeks)               (variable)                 (ongoing)           │
│                                                                         │
│  ┌──────────┐           ┌──────────────┐           ┌──────────────┐    │
│  │Experiment│  "Fill"   │   Product    │  Scale    │  Standalone  │    │
│  │   Pod    │ ────────► │    Team      │ ────────► │   Business   │    │
│  │  (3 ppl) │           │  (5-8 ppl)   │           │    Unit      │    │
│  └──────────┘           └──────────────┘           └──────────────┘    │
│                                                                         │
│  Labs owns               Own P&L                    Reports to CEO/     │
│  100%                    Still AIAD-native          product leadership  │
│                          Hires around core                              │
│                          Labs principles apply                          │
│                                                                         │
└─────────────────────────────────────────────────────────────────────────┘
```

**What this means:**
- Labs stays lean (incubator, not accumulator)
- Successful products get dedicated resources without bloating Labs
- Spinout teams maintain AIAD culture from Labs DNA
- Legacy never absorbs Labs products (prevents culture dilution)
- Each spinout becomes a potential mini-business unit

---

## Process in AIAD

### The Death of Sequential Process

Traditional software process exists because of **latency**—the gap between intent and artifact:

```
Traditional: Idea → Spec → Design Review → Build → Code Review → QA → Ship
```

Each gate exists because changing the artifact is expensive. You review designs before building because building is slow. You review code before merging because fixing is costly. Process is a hedge against the cost of iteration.

### The AIAD Collapse

When creation becomes real-time dialog with AI, these gates collapse:

```
AIAD: Intent ↔ Artifact (continuous)
```

**The review is the creation.** You don't spec → review → build. You converse with the artifact directly:

- "Make this button more prominent" → *it changes*
- "That broke the layout" → *it fixes*
- "Actually, let's try a different approach" → *it pivots*

The feedback loop is so tight that traditional review becomes meaningless.

### What Remains

**Intent Clarification:** You still need to know what you're building. But instead of writing specs that get reviewed, you explore intent through prototypes. The prototype is the spec.

**Quality Judgment:** Humans still decide "is this good enough?" But the judgment happens in the moment, not in a review meeting next week.

**Architectural Decisions:** Big structural choices still matter. But even here, AIAD compresses the cycle: prototype both approaches in a day, feel the difference, decide.

**User Feedback:** The ultimate review is still users. Ship fast, watch metrics, iterate.

### The New Workflow

**Before: Waterfall with Agile Lipstick**
```
Monday: Sprint planning (2 hours)
Tuesday-Thursday: Build
Friday: Code review, QA
Next Monday: Retro, planning again
Repeat for 6 sprints
Ship something
```

**After: Continuous Dialog**
```
Morning: "Here's what I'm thinking" → prototype exists
Midday: "Users are saying X" → iterate
Afternoon: Ship to beta
Tomorrow: "Metrics show Y" → adjust
Repeat daily
```

The unit of work isn't the sprint. It's the **conversation turn**.

### What This Means for Labs

**No Design Reviews:** Don't schedule meetings to review designs. Show the working thing. If it's wrong, change it while everyone watches.

**No Code Reviews (Traditional):** Code review as gate-keeping is dead. The AI already reviewed it. You already iterated on it through conversation. What remains: pair programming, post-hoc learning, architecture discussions before major structural changes.

**No Handoffs:** In traditional process, you hand off: design → eng → QA → ops. In AIAD, the same person (Builder + AI) takes intent to production. No handoffs means no handoff meetings, no handoff documentation, no handoff delays.

**No Roadmaps Beyond 8 Weeks:** Roadmaps exist because execution is slow and change is expensive. When you can build anything in days, why plan months ahead?

### The New Rituals

**Daily Standup Video:** Not "Yesterday I did X, today I'll do Y." Instead: 60-second screen recording showing what you shipped. Posted publicly. The artifact speaks for itself.

**Weekly Demo:** Not slideshow of what we plan to build. Instead: Live walkthrough of working software. Users can try it. Feedback happens in real-time.

**8-Week Fill/Kill:** Not project review with status updates. Instead: Binary decision based on metrics. Does it work? Ship or kill. No extended deliberation.

---

## Operating Model

### Remote-First

**Why remote for Labs:**
- Access to global AIAD talent pool
- Forces async discipline (documentation, written communication)
- Natural "black box" from Legacy (no hallway conversations pulling them back)
- Cost efficiency (can hire outside expensive markets)
- Aligns with "build in public" digital-native culture

**How it works:**
- Fully distributed team
- Async by default, sync when needed
- Daily standup videos (not calls)
- Weekly demo calls (recorded for async viewing)
- No physical office required
- Optional co-working stipend

### Discord as the Office

```
#general - Team chat
#announcements - Public updates (visible to community)
#experiment-alpha - Experiment-specific work channel
#experiment-beta - Experiment-specific work channel
#platform - Infrastructure discussion
#builds - Deployment notifications
#metrics - Automated dashboards
#community - User feedback
#random - Social/fun
```

All work happens in public channels. Decisions documented in real-time. Community sees the work as it happens.

### Timezone Strategy

**Preferred: Primary timezone overlap (4 hours)**
- Core hours for sync when needed
- Team distributed across compatible regions
- Async communication for everything else

---

## The AIAD Toolchain

### Every Labs Person Uses

| Tool | Purpose |
|------|---------|
| Claude Code / Cursor | Primary development environment |
| GitHub Copilot | Code completion |
| v0 / Vercel | UI prototyping |
| Midjourney / DALL-E | Visual assets |
| Claude / ChatGPT | Research, writing, planning |
| Notion AI | Documentation |
| Loom | Async video updates |
| Linear | Lightweight task tracking |
| Discord | Team + community hub |
| Figma | Design collaboration |

### AI-First Development Principles

1. **Prompt before code** - Describe what you want, let AI draft it
2. **AI review before merge** - Ask Claude to review the PR
3. **AI docs** - Generate documentation from code
4. **AI testing** - Generate test cases automatically
5. **Human judgment on architecture** - AI accelerates, humans decide

---

## Hiring for AIAD

### What Makes a "Labs Person"

**Must Have:**
1. **AIAD fluency** - Already using Claude Code, Cursor, etc. in their workflow
2. **Bias for shipping** - Portfolio of things they've actually launched
3. **Comfort with ambiguity** - No PRDs, no detailed specs, just problems to solve
4. **Public accountability** - Willingness to build in public, show failures
5. **Speed over perfection** - 80% solution today beats 100% next month

**Nice to Have:**
- Experience at early-stage startups
- Side projects they've launched
- Content creation experience
- Domain expertise

**Red Flags:**
- Wants detailed requirements before starting
- Uncomfortable with AI coding assistants
- Prefers large team collaboration
- Asks about code review process
- Concerned about "proper" architecture

### Hiring Bar

- Must demonstrate AIAD workflow in interview (live coding with AI tools)
- Must have shipped something publicly in last 12 months
- Must be comfortable with radical transparency

### Mostly External

**Why external:**
- AIAD fluency is rare in traditional orgs
- Avoids importing legacy mindset
- Fresh perspectives on speed
- No "but we've always done it this way"

**Where to find them:**
- Indie hackers, solopreneurs, ex-startup founders
- Build in public attracts talent who see the work
- Remote-first expands talent pool globally

---

## Budget Model

### Annual Labs Budget (Example: 2 Pods + Platform)

| Category | Cost |
|----------|------|
| **People** | |
| 4 Builders @ $180K | $720K |
| 2 Amplifiers @ $100K | $200K |
| 3 Platform @ $170K avg | $510K |
| 1 DevOps @ $160K | $160K |
| **Subtotal People** | **$1.59M** |
| | |
| **Infrastructure** | |
| Cloud/SaaS tools | $120K |
| Co-working stipends | $36K |
| Equipment | $30K |
| Travel (quarterly gatherings) | $40K |
| **Subtotal Ops** | **$226K** |
| | |
| **Total Labs** | **~$1.8M** |

**Compared to traditional approach:**
- 20-person local team would cost $4-5M
- Labs delivers same/more output for ~40% of cost
- Plus: faster shipping, more experiments, AIAD leverage

---

## Risk Mitigation

### Risk: Labs culture dilutes over time

**Mitigation:**
- CTO direct oversight protects independence
- Hiring bar stays high (AIAD fluency required)
- Successful products spin out (Labs stays small)
- Remote separation from Legacy

### Risk: Remote team lacks cohesion

**Mitigation:**
- Quarterly in-person gatherings
- Strong Discord culture
- Daily video updates create connection
- Build-in-public creates shared purpose

### Risk: AIAD-native talent is hard to find

**Mitigation:**
- Look at indie hackers, solopreneurs, ex-startup founders
- Build in public attracts talent who see the work
- Remote-first expands talent pool globally

### Risk: Experiments fail publicly

**Mitigation:**
- This is a feature, not a bug
- Failures show learning, build trust
- Kill fast, don't drag out embarrassment
- Frame as "we tried and learned"

---

## Implementation Checklist

### Phase 1: Foundation (Weeks 1-4)

- [ ] CTO commits to direct Labs oversight
- [ ] Establish Labs as separate org unit
- [ ] Set up Labs infrastructure (separate from Legacy)
- [ ] Create Labs Discord server
- [ ] Hire Platform Lead
- [ ] Hire first 2 Builders (1 per experiment)

### Phase 2: First Experiments (Weeks 5-12)

- [ ] Platform Lead sets up shared infrastructure
- [ ] Complete pod hiring (second Builder + Amplifier per pod)
- [ ] Launch first 2 experiments
- [ ] Both experiments hit Week 8 milestones
- [ ] Fill/Kill decisions made

### Phase 3: Scale (Weeks 13+)

- [ ] Spinout process for successful experiments
- [ ] Add experiment pods as needed
- [ ] Promote Labs Lead from within (when CTO bandwidth constrained)
- [ ] Establish Interface Committee rhythm

---

## Summary

The AIAD Labs Framework is built on three core insights:

1. **AI has inverted the cost structure of building software.** Traditional process was a hedge against iteration cost. That cost is now near zero.

2. **Small teams with AI leverage outperform large teams without it.** A 3-person pod shipping daily beats a 20-person team shipping quarterly.

3. **Innovation requires protection from the mothership.** You cannot run AIAD inside a traditional org. Labs must be black-boxed, with clean interfaces to Legacy.

The result: an organizational structure optimized for the new economics of software development, where the unit of work is the conversation turn and the review is the creation itself.
