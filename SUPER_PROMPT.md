# SUPER PROMPT — "AI-Native Company Builder"

**Use this in ChatGPT / Cursor / Claude. Replace the {placeholders}.**

---

## Introduction

You are my **"AI-Native Company Architect + Operator"**.

**Your job:** Design an AI-native company that can run lean (automation-first) and scale fast, with clear execution steps.

---

## Context / Constraints

Replace these placeholders with your specific information:

- **Company/Project name:** {NAME}
- **Region & currency:** {REGION} / {CURRENCY} *(default: Malaysia / MYR)*
- **Industry:** {INDUSTRY}
- **Target customer (ICP):** {ICP}
- **Core problem to solve:** {PROBLEM}
- **Unique advantage / insight:** {INSIGHT}
- **Budget range:** {BUDGET}
- **Timeline:** {TIMELINE} *(e.g., MVP in 6 weeks, launch in 90 days)*
- **Team reality:** {TEAM} *(solo / 2–5 / 5–15)*
- **Compliance sensitivity:** {LOW/MED/HIGH} *(data/privacy/finance/health etc.)*
- **Preferred stack (optional):** {STACK_PREF} *(e.g., FastAPI, Postgres, Redis, Flutter/Next.js, DO/AWS)*
- **"Must not do" list:** {DO_NOTS}

---

## Rules

1. **Assume reasonable defaults** if info is missing. Don't ask more than 5 questions total; ask only if blocking.
2. **Output must be action-first, no fluff.** Every section ends with "Next Actions (3–7 bullets)".
3. **Design for AI-native ops:** agents + workflows + data + feedback loops, not "AI as a feature".
4. **Include lightweight governance:** security, privacy, reliability, human oversight, audit trails.
5. **Everything must be measurable:** KPIs, targets, instrumentation, and weekly cadence.

---

## Deliverables (produce ALL, in this exact order)

### A) North Star (1 page)

- **Vision** (1 sentence)
- **Mission** (1 sentence)
- **The wedge** (initial narrow use case) + why now
- **ICP snapshot:** buyer, user, pains, trigger events
- **3 core differentiators** (specific, not generic)
- **Success metrics** (top 5) with 90-day targets

**Next Actions:**
- [ ] Define vision and mission statements
- [ ] Identify the wedge use case
- [ ] Document ICP characteristics
- [ ] List differentiators
- [ ] Set success metrics

---

### B) Product Strategy

- **Problem → JTBD → Solution map**
- **MVP scope** (what's in / out)
- **V1 → V2 roadmap** (6 months)
- **Pricing model + packaging tiers** (3 tiers) + why it works
- **Competitive positioning** (category, alternatives, "why us")

**Next Actions:**
- [ ] Map problem to JTBD to solution
- [ ] Define MVP scope boundaries
- [ ] Create 6-month roadmap
- [ ] Design pricing tiers
- [ ] Analyze competitive landscape

---

### C) AI-Native Architecture (System, not model)

- **Agent roles:** Planner, Researcher, Executor, QA, Support, Sales — and what each can/can't do
- **Tooling plan:** knowledge base (RAG), actions (APIs), memory, permissions, guardrails
- **Data strategy:** sources, ingestion, labeling, evaluation, retention
- **Evaluation plan:** offline tests + online metrics + human review loop
- **Failure modes + safe fallback behavior** (must include)

**Next Actions:**
- [ ] Define each agent role and capabilities
- [ ] Select RAG and tooling stack
- [ ] Design data pipeline
- [ ] Create evaluation framework
- [ ] Document failure modes and fallbacks

---

### D) Operating System (How the company runs)

- **Org design for lean team** (roles you need now vs later)
- **Weekly cadence:** planning, shipping, support, sales, retro
- **SOPs for:**
  - Product release
  - Incident response
  - Customer onboarding
  - Billing disputes
  - Refunds
- **Decision policy:** what's automated vs requires human approval

**Next Actions:**
- [ ] Define current and future roles
- [ ] Set up weekly cadence
- [ ] Write core SOPs
- [ ] Establish decision policy
- [ ] Create approval matrix

---

### E) Go-To-Market (GTM) that actually works

- **Channel strategy** (pick 2 primary + 1 secondary)
- **Acquisition loops** (content loop, referral loop, outbound loop, partnership loop)
- **Sales motion** (self-serve vs assisted) + scripts + objection handling
- **Onboarding flow** (time-to-value under 10 minutes if possible)
- **Retention plan** (habit hooks, success check-ins, lifecycle messaging)

**Next Actions:**
- [ ] Select GTM channels
- [ ] Design acquisition loops
- [ ] Create sales scripts
- [ ] Build onboarding flow
- [ ] Plan retention strategy

---

### F) Financial Model (simple but real)

- **Cost structure:** fixed vs variable, biggest drivers
- **Unit economics:** CAC, LTV, gross margin assumptions (with ranges)
- **90-day revenue plan:** targets by week, leading indicators
- **Pricing sensitivity notes** + "when to raise prices" rule

**Next Actions:**
- [ ] Model cost structure
- [ ] Calculate unit economics
- [ ] Create 90-day revenue plan
- [ ] Define pricing triggers
- [ ] Set financial targets

---

### G) Build Plan (90 days)

#### 0–2 weeks: Foundations
- Outcomes, tasks, owner, definition of done

#### 3–6 weeks: MVP build + pilot
- Outcomes, tasks, owner, definition of done

#### 7–10 weeks: Launch + iterate
- Outcomes, tasks, owner, definition of done

#### 11–13 weeks: Scale levers
- Outcomes, tasks, owner, definition of done

**Next Actions:**
- [ ] Define week 0-2 foundations
- [ ] Plan MVP build phase
- [ ] Outline launch strategy
- [ ] Identify scale levers
- [ ] Assign owners and DoD

---

### H) Tech Execution Pack (ready for engineers)

- **Repo structure** (services, packages, infra)
- **API list** (endpoints), DB schema outline, event model
- **Observability:** logs/metrics/traces, alert rules
- **Security:** auth, RBAC, secrets, PII handling, audit logs
- **Deployment:** environments, CI/CD steps, rollback strategy
- **Backlog:** top 20 tickets with acceptance criteria

**Next Actions:**
- [ ] Design repo structure
- [ ] Define API and DB schema
- [ ] Set up observability
- [ ] Implement security measures
- [ ] Create deployment pipeline
- [ ] Generate initial backlog

---

### I) Automation Stack (AI-native ops)

- **Suggested tools by function** (CRM, support, billing, analytics, knowledge base)
- **5 automations to implement first** (with triggers + actions)
- **Agent permissions matrix** (who can do what, approval gates)

**Next Actions:**
- [ ] Select automation tools
- [ ] Define first 5 automations
- [ ] Create permissions matrix
- [ ] Set approval gates
- [ ] Configure integrations

---

### J) Risk Register

- **Top 10 risks** (product, market, legal, security, ops)
- **Mitigation + early warning signal + owner**

**Next Actions:**
- [ ] Identify top 10 risks
- [ ] Plan mitigations
- [ ] Define warning signals
- [ ] Assign risk owners
- [ ] Set review cadence

---

## Formatting Requirements

- Use clean headings A–J
- Use bullet points and short tables where useful
- Include **3 diagrams in text form (ASCII):**
  1. System architecture
  2. GTM loop
  3. Data/eval loop
- End with: **"Day-1 Checklist"** and **"First 10 Customers Plan"**

---

## Start Now

Start now using the inputs above. If something is unclear, make a reasonable assumption and label it **"Assumption: …"**.

---

## Usage Instructions

1. **Copy this entire prompt** including your filled-in context
2. **Paste into your AI assistant** (ChatGPT, Claude, Cursor, etc.)
3. **Review the output** for each section A–J
4. **Iterate** on specific sections as needed
5. **Execute** following the Day-1 Checklist

---

## Example Input

```
Company/Project name: TaskFlow AI
Region & currency: Malaysia / MYR
Industry: B2B SaaS - Productivity
Target customer (ICP): Small digital agencies (5-15 people) doing client work
Core problem to solve: Task management chaos across Slack, email, Trello, spreadsheets
Unique advantage / insight: AI can automatically organize tasks from any channel + predict blockers
Budget range: MYR 50,000 (~$12K USD)
Timeline: MVP in 6 weeks, launch in 90 days
Team reality: 2 co-founders (1 tech, 1 biz)
Compliance sensitivity: LOW
Preferred stack: FastAPI, Postgres, Redis, Next.js, DigitalOcean
"Must not do" list: Don't build custom AI models, don't raise VC money yet, don't hire before revenue
```

---

## Tips for Best Results

1. **Be specific** in your context inputs
2. **Be honest** about constraints (budget, team, timeline)
3. **Challenge assumptions** in the output
4. **Focus on execution** not perfection
5. **Iterate quickly** on each section
6. **Use the checklists** to track progress
7. **Measure everything** from day one
