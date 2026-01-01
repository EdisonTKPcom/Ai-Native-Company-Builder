# Quick Start Guide — AI-Native Company Builder

**Get from idea to blueprint in 10 minutes.**

---

## 🎯 Goal

Transform your business idea into a complete, executable company blueprint with:
- Product strategy
- AI architecture
- Go-to-market plan
- Financial model
- 90-day build plan
- Day-1 checklist

---

## ⚡ Quick Start (3 Steps)

### Step 1: Prepare Your Inputs (5 minutes)

Fill in these key details:

```
Company/Project name: [Your company name]
Region & currency: [e.g., USA / USD, Malaysia / MYR]
Industry: [e.g., B2B SaaS, E-commerce, FinTech]
Target customer (ICP): [Who are you building for?]
Core problem to solve: [What pain are you addressing?]
Unique advantage: [What do you have that others don't?]
Budget range: [e.g., $5K, $50K, $100K]
Timeline: [e.g., MVP in 6 weeks, launch in 90 days]
Team reality: [solo / 2-5 people / describe your team]
Compliance sensitivity: [LOW / MED / HIGH]
Preferred stack: [e.g., FastAPI, Postgres, Next.js, AWS]
"Must not do" list: [Constraints you have]
```

**Need help?** See [TEMPLATE.md](./TEMPLATE.md) for 3 complete examples.

---

### Step 2: Use the Prompt (2 minutes)

1. **Copy** your filled-in inputs from Step 1
2. **Copy** the entire [SUPER_PROMPT.md](./SUPER_PROMPT.md) content
3. **Open** ChatGPT (GPT-4), Claude (Opus/Sonnet), or Cursor
4. **Paste** both your inputs + the SUPER_PROMPT together
5. **Press** Enter

The AI will generate your complete blueprint in ~3 minutes.

---

### Step 3: Review & Execute (3 minutes)

1. **Scan** the output — all sections A through J
2. **Save** the output as `YOUR_COMPANY_blueprint.md`
3. **Review** the Day-1 Checklist at the end
4. **Start** executing immediately

---

## 📋 What You'll Get

### Section A: North Star
- Vision & mission (1 sentence each)
- Your wedge (initial narrow use case)
- ICP snapshot (who's the buyer, what's their pain)
- 3 core differentiators
- Success metrics with 90-day targets

### Section B: Product Strategy
- Problem → JTBD → Solution map
- MVP scope (what's in, what's out)
- 6-month roadmap
- Pricing model (3 tiers)
- Competitive positioning

### Section C: AI-Native Architecture
- Agent roles (Planner, Researcher, Executor, QA, Support, Sales)
- Tooling plan (RAG, APIs, memory, guardrails)
- Data strategy (sources, ingestion, labeling, evaluation)
- Evaluation plan (offline tests, online metrics, human review)
- Failure modes + fallbacks

### Section D: Operating System
- Org design (roles now vs later)
- Weekly cadence (planning, shipping, support, retro)
- SOPs (product release, incidents, onboarding, billing, refunds)
- Decision policy (what's automated vs needs approval)

### Section E: Go-To-Market
- Channel strategy (2 primary + 1 secondary)
- Acquisition loops (content, referral, outbound, partnership)
- Sales motion (self-serve vs assisted, scripts, objection handling)
- Onboarding flow (<10 min to value)
- Retention plan (habit hooks, check-ins, lifecycle messaging)

### Section F: Financial Model
- Cost structure (fixed vs variable)
- Unit economics (CAC, LTV, gross margin)
- 90-day revenue plan (weekly targets)
- Pricing sensitivity notes

### Section G: Build Plan (90 days)
- Week 0-2: Foundations
- Week 3-6: MVP build + pilot
- Week 7-10: Launch + iterate
- Week 11-13: Scale levers
- (Each phase: outcomes, tasks, owner, definition of done)

### Section H: Tech Execution Pack
- Repo structure
- API list + DB schema
- Observability (logs/metrics/traces)
- Security (auth, RBAC, secrets, PII, audit logs)
- Deployment (environments, CI/CD, rollback)
- Backlog (top 20 tickets with acceptance criteria)

### Section I: Automation Stack
- Suggested tools by function (CRM, support, billing, analytics)
- 5 automations to implement first
- Agent permissions matrix

### Section J: Risk Register
- Top 10 risks (product, market, legal, security, ops)
- Mitigation + early warning signals + owners

### Plus Diagrams & Checklists
- 3 ASCII diagrams (architecture, GTM loop, data/eval loop)
- Day-1 Checklist (ready to execute)
- First 10 Customers Plan (specific tactics)

---

## 💡 Tips for Best Results

### Be Specific
❌ "SaaS startup"  
✅ "B2B SaaS for dental clinics managing patient appointments"

### Be Realistic
❌ "$1M budget" when you have $10K  
✅ "$10K bootstrapped budget, willing to do outbound sales myself"

### Be Honest About Constraints
❌ Leaving "Must not do" blank  
✅ "Don't build mobile app yet, don't raise VC money, don't hire before $10K MRR"

### Be Clear on ICP
❌ "Small businesses"  
✅ "Instagram/TikTok sellers doing $10K-100K/month in Southeast Asia"

### Include Numbers
❌ "Get some customers"  
✅ "10 paying customers by week 12, $15K MRR target"

---

## 📖 Example Input

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

**See full output:** [EXAMPLE_OUTPUT.md](./EXAMPLE_OUTPUT.md)

---

## 🚀 After You Get Your Blueprint

### Week 0 (Setup)
- [ ] Register domain
- [ ] Set up repo
- [ ] Create accounts (cloud, payments, email, AI APIs)
- [ ] Deploy "coming soon" page

### Week 1 (Foundations)
- [ ] Build auth (signup/login)
- [ ] Build core integration (Slack, Stripe, etc.)
- [ ] Set up database
- [ ] Create CI/CD pipeline

### Week 2-4 (MVP)
- [ ] Build MVP features (from your blueprint)
- [ ] Test with pilot customers
- [ ] Fix critical bugs
- [ ] Iterate based on feedback

### Week 5+ (Launch & Grow)
- [ ] Public launch
- [ ] Customer acquisition (follow GTM plan)
- [ ] Iterate weekly
- [ ] Track towards targets

---

## 🎓 Learn More

- **Full prompt:** [SUPER_PROMPT.md](./SUPER_PROMPT.md)
- **Input template:** [TEMPLATE.md](./TEMPLATE.md) (with 3 examples)
- **Example output:** [EXAMPLE_OUTPUT.md](./EXAMPLE_OUTPUT.md) (TaskFlow AI)
- **Usage guide:** [README.md](./README.md)

---

## ❓ FAQ

**Q: Which AI should I use?**  
A: ChatGPT (GPT-4), Claude (Opus or Sonnet), or Cursor. All work well.

**Q: How long does it take?**  
A: 5 min to fill inputs + 3 min for AI to generate = 8-10 minutes total.

**Q: Can I iterate on sections?**  
A: Yes! Ask the AI to regenerate specific sections or go deeper on certain areas.

**Q: Do I need coding skills?**  
A: No. The blueprint is designed for non-technical founders too. You can hand the Tech Execution Pack to a developer.

**Q: What if I don't know my ICP yet?**  
A: Make your best guess. The AI will help you refine it. You can regenerate after customer discovery.

**Q: Can I customize the prompt?**  
A: Absolutely! Edit [SUPER_PROMPT.md](./SUPER_PROMPT.md) to add/remove sections as needed.

---

## ✅ Success Criteria

You know the blueprint is good when:

- [ ] You can start executing the Day-1 Checklist immediately
- [ ] The MVP scope is clear (what's in, what's out)
- [ ] You know exactly who your first 10 customers are
- [ ] You have a weekly plan for 90 days
- [ ] Financial model makes sense for your budget
- [ ] You feel excited (not overwhelmed)

---

## 🤝 Need Help?

- **Questions?** Check [EXAMPLE_OUTPUT.md](./EXAMPLE_OUTPUT.md)
- **Issues?** Open a GitHub issue
- **Want to share?** Submit your success story via PR

---

**Ready? Let's build.** 🚀

1. Fill in your inputs (5 min)
2. Paste into ChatGPT/Claude (2 min)
3. Review your blueprint (3 min)
4. Start building (Day 1)
