# TaskFlow AI — Company Blueprint

*Generated using AI-Native Company Builder*

**Input Context:**
- Company: TaskFlow AI
- Region: Malaysia / MYR
- Industry: B2B SaaS - Productivity
- ICP: Small digital agencies (5-15 people)
- Problem: Task management chaos across channels
- Timeline: MVP in 6 weeks, launch in 90 days
- Team: 2 co-founders (1 tech, 1 biz)
- Budget: MYR 50,000 (~$12K USD)

---

## A) North Star

### Vision
TaskFlow AI becomes the default operating system for every digital agency under 50 people in Southeast Asia.

### Mission
We eliminate task management chaos by automatically organizing work from any channel into intelligent workflows.

### The Wedge (Why Now)
**Initial Use Case:** Auto-capture tasks from Slack channels → smart prioritization → deadline alerts

**Why Now:**
- Remote/hybrid work = more chat-based communication = more chaos
- GPT-4 can reliably extract tasks from unstructured text
- Agencies bleeding time on "what's the status" questions

### ICP Snapshot

| Dimension | Details |
|-----------|---------|
| **Buyer** | Agency founder/ops manager |
| **User** | Project managers + team leads |
| **Pain** | Spend 2-3 hours/day chasing task status across tools |
| **Trigger Event** | Missed client deadline, team confusion, tool sprawl |
| **Size** | 5-15 people, $50K-300K monthly revenue |
| **Channels** | Use Slack + (Trello/Asana/Notion) + email + spreadsheets |

### 3 Core Differentiators

1. **Channel-agnostic task capture:** Works in Slack, email, Trello — no behavior change required
2. **Predictive blockers:** AI flags tasks likely to miss deadlines 48hrs before (not just reminders)
3. **Malaysia-first pricing:** MYR 99/user/mo (half of Asana/Monday.com when converted)

### Success Metrics (90-day targets)

| Metric | Target | Measurement |
|--------|--------|-------------|
| **Active agencies** | 15 paying | Stripe active subscriptions |
| **Tasks auto-captured** | 5,000+ | DB count where source != "manual" |
| **Time saved per user/week** | 2 hours | User survey + activity logs |
| **NPS** | 40+ | Monthly survey |
| **Weekly active rate** | 70%+ | Users logging in 3+ days/week |

**Next Actions:**
- [x] Vision and mission defined
- [ ] Validate ICP with 10 agency interviews
- [ ] Set up analytics to track success metrics
- [ ] Create differentiator talking points for sales
- [ ] Build dashboard to monitor 90-day targets

---

## B) Product Strategy

### Problem → JTBD → Solution Map

```
PROBLEM
├─ Tasks scattered across Slack, email, Trello, spreadsheets
├─ Status updates require manual checking
└─ Deadlines missed due to lack of visibility

JOBS TO BE DONE
├─ "Help me capture every task without changing how we work"
├─ "Show me what's at risk before it's late"
└─ "Give me one source of truth for team workload"

SOLUTION
├─ AI task extraction from all channels (Slack, email, tools)
├─ Predictive blocker detection (AI + heuristics)
└─ Unified dashboard with team view + individual view
```

### MVP Scope

**IN:**
- Slack integration (capture tasks from messages)
- Manual task creation (web app)
- Basic task list view (by person, by project, by deadline)
- Email digest (daily summary of tasks)
- Blocker prediction (simple heuristics: overdue, no activity)

**OUT:**
- Email/Trello/Asana integrations (V2)
- Mobile app (V2)
- Time tracking (maybe never)
- Gantt charts (not our wedge)
- Team chat (use Slack)

### V1 → V2 Roadmap (6 months)

| Phase | Timeline | Key Features |
|-------|----------|--------------|
| **MVP** | Week 0-6 | Slack integration, task list, manual entry, email digest |
| **V1.1** | Week 7-10 | Email integration (Gmail), improved blocker AI, filters |
| **V1.2** | Week 11-14 | Trello/Asana import, recurring tasks, team workload view |
| **V2** | Week 15-24 | Mobile app, custom workflows, API, advanced analytics |

### Pricing Model + Packaging Tiers

| Tier | Price (MYR/user/mo) | Features | Why It Works |
|------|---------------------|----------|--------------|
| **Starter** | 49 | 1 integration (Slack), 100 tasks/mo, email digest | Low barrier to try, converts to Pro |
| **Pro** | 99 | Unlimited integrations, unlimited tasks, blocker AI, team views | Sweet spot for 5-15 person agencies |
| **Agency** | 249 | Everything + API, custom workflows, priority support | 15+ people, willing to pay for customization |

**Why It Works:**
- Starter = land (free trial converts here)
- Pro = expand (most revenue, clear value prop)
- Agency = upsell (high-touch, relationship-based)

**Assumption:** 70% of customers will be Pro tier

### Competitive Positioning

**Category:** AI-powered task management for agencies

**Alternatives:**
- Asana/Monday.com (too complex, expensive when converted to MYR)
- Trello (no AI, no cross-channel capture)
- Notion (docs-first, weak on task management)
- Custom spreadsheets (manual, no automation)

**"Why Us":**
- Only tool that captures tasks from Slack without changing workflows
- Predictive blockers (not reactive reminders)
- Built for SEA agencies (pricing, support, localization)

**Next Actions:**
- [ ] Build MVP feature set (Slack integration + task list)
- [ ] Create pricing page with tier comparison
- [ ] Set up Stripe for billing
- [ ] Draft competitive comparison doc for sales
- [ ] Interview 5 agencies to validate roadmap

---

## C) AI-Native Architecture

### Agent Roles

| Agent | Can Do | Can't Do |
|-------|--------|----------|
| **Task Extractor** | Parse Slack messages, emails for tasks; extract title, assignee, deadline | Create tasks without 70%+ confidence; modify existing tasks |
| **Blocker Predictor** | Flag tasks at risk of missing deadlines; suggest who to notify | Auto-reassign tasks; send messages without approval |
| **Digest Generator** | Create daily/weekly summaries; personalize per user | Send before 6am or after 10pm user local time |
| **Support Bot** | Answer product questions; route to human for bugs/billing | Process refunds; access user data without permission |
| **Sales Assistant** | Qualify leads from form; book demos; send follow-ups | Negotiate pricing; make promises about features |

### Tooling Plan

**Knowledge Base (RAG):**
- Embed user's task history, Slack context, project docs
- Vector DB: Pinecone (free tier: 1M vectors)
- Embedding: OpenAI text-embedding-3-small

**Actions (APIs):**
- Slack API (read messages, post notifications)
- Email API (Gmail via OAuth, SendGrid for digests)
- Stripe API (billing, subscription management)
- Internal API (CRUD on tasks, projects, users)

**Memory:**
- User preferences (digest frequency, notification settings)
- Task history (who created, who completed, how long)
- Blocker patterns (what predicted blockers were accurate)

**Permissions:**
- Task Extractor: Read Slack, write tasks (draft mode)
- Blocker Predictor: Read tasks, write predictions
- Support Bot: Read docs, write messages (approved templates)
- Sales Assistant: Read leads, write CRM, send emails (pre-approved)

**Guardrails:**
- No task deletion by AI (only archive)
- No messages sent to customers without human review (first 30 days)
- No data shared across companies (strict tenant isolation)
- Rate limits on all agents (prevent runaway costs)

### Data Strategy

**Sources:**
- Slack messages (via API, real-time + backfill)
- Manual task creation (web app)
- Email (Gmail API, IMAP)
- Future: Trello, Asana, Notion

**Ingestion:**
- Slack: Webhook + nightly backfill job
- Email: Poll every 15 min
- Manual: Immediate

**Labeling:**
- Initial: Human review of 500 AI-extracted tasks (correct/incorrect)
- Ongoing: Users can mark AI task as incorrect → feedback loop

**Evaluation:**
- Offline: Precision/recall on test set (500 labeled messages)
- Online: User edits task after AI creation = implicit feedback
- Human review: Weekly audit of 100 random AI tasks

**Retention:**
- Active tasks: Keep forever
- Archived tasks: 2 years
- Slack messages: 30 days (compliance)
- AI predictions: 90 days (audit)

### Evaluation Plan

**Offline Tests (before deploy):**
- Task extraction accuracy: >85% precision, >75% recall
- Blocker prediction: Test on historical data (did we predict actual blockers?)
- Digest quality: Human review of 20 generated digests

**Online Metrics (in production):**
- Task extraction acceptance rate (users keep vs delete AI tasks)
- Blocker prediction hit rate (flagged tasks that actually missed deadline)
- Digest open rate + click-through rate

**Human Review Loop:**
- Weekly: Review 100 random AI-extracted tasks
- Monthly: Review all blocker predictions from past week
- Quarterly: Full audit of AI decisions + retrain if needed

### Failure Modes + Safe Fallback

| Failure | Impact | Fallback | Prevention |
|---------|--------|----------|------------|
| **AI extracts wrong task** | User wastes time deleting | AI tasks marked as "draft", user must approve | Confidence threshold >70% |
| **Blocker prediction false alarm** | Notification fatigue | Max 3 blocker alerts/week per user | Tune prediction threshold |
| **Slack API down** | No new tasks captured | Queue events, retry 3x, alert admin | Health check every 5 min |
| **OpenAI API limit hit** | AI features break | Fallback to manual mode, show banner | Monitor quota, alert at 80% |
| **Data leak (wrong company)** | Security breach | Tenant isolation in DB, row-level security | Automated tests + manual audit |

**Next Actions:**
- [ ] Define agent roles and permissions in code
- [ ] Set up Pinecone + OpenAI APIs
- [ ] Build task extraction with confidence scoring
- [ ] Create blocker prediction heuristics (v1: simple rules)
- [ ] Implement failure mode fallbacks
- [ ] Set up evaluation dashboard

---

## D) Operating System (How the company runs)

### Org Design for Lean Team

**Now (Week 0-12):**
- **Founder 1 (Tech):** Product, engineering, infrastructure
- **Founder 2 (Biz):** Sales, marketing, customer success, ops

**Later (Week 13+):**
- **First hire (Week 16):** Customer success / support (part-time)
- **Second hire (Week 24):** Full-stack engineer (contract)

**Assumption:** No full-time hires until MYR 30K MRR

### Weekly Cadence

| Day | Activity | Owner | Duration |
|-----|----------|-------|----------|
| **Monday 9am** | Weekly planning (priorities, blockers) | Both | 30 min |
| **Tuesday 4pm** | Product demo (what shipped last week) | Tech | 15 min |
| **Wednesday 10am** | Customer check-ins (3-5 customers) | Biz | 2 hours |
| **Thursday 3pm** | Sales pipeline review | Biz | 30 min |
| **Friday 5pm** | Retro (what worked, what didn't) | Both | 45 min |

**Daily:** 
- Async standup in Slack (by 10am): yesterday, today, blockers
- Support tickets reviewed by noon

### SOPs

#### Product Release
1. Code complete + tests pass
2. Deploy to staging, test manually (1 hour)
3. Deploy to production (Friday 10am-2pm only, not after 2pm)
4. Monitor errors for 2 hours
5. Announce in customer Slack + changelog
6. If critical bug, rollback immediately

#### Incident Response
1. Customer reports bug → acknowledge within 30 min
2. Severity assessment: P0 (broken), P1 (degraded), P2 (cosmetic)
3. P0: Drop everything, fix + deploy within 4 hours
4. P1: Fix within 24 hours
5. P2: Add to backlog
6. Post-mortem for all P0 incidents (root cause + prevention)

#### Customer Onboarding
1. Trial signup → automated email (how to connect Slack)
2. Connected Slack → automated email (how to create first task)
3. Day 3: Biz founder sends personal check-in email
4. Day 7: Offer 15-min onboarding call
5. Day 14: Convert to paid or send "what's blocking you?" email

#### Billing Disputes
1. Customer claims incorrect charge
2. Check Stripe + usage logs
3. If our error: Refund immediately + apologize + give 1 month free
4. If customer error: Explain politely, offer to downgrade if over budget
5. Escalate to founder if >MYR 500

#### Refunds
1. Request within 30 days: Full refund, no questions
2. Request 31-60 days: 50% refund if unused
3. Request 60+ days: Case-by-case (founder decision)
4. Process via Stripe within 24 hours
5. Follow-up email: "What could we have done better?"

### Decision Policy

**Automated:**
- Task extraction (if confidence >70%)
- Digest sending (per user schedule)
- Trial → paid conversion (if payment succeeds)
- Support: Answering product questions from docs

**Requires Human Approval:**
- Blocker notifications (first 30 days, then auto if >80% accuracy)
- Refunds >MYR 500
- Pricing changes
- New integrations
- Data deletion requests

**Next Actions:**
- [ ] Set up Monday planning template
- [ ] Write SOPs in Notion
- [ ] Create incident severity rubric
- [ ] Build onboarding email sequence
- [ ] Configure refund policy in Stripe

---

## E) Go-To-Market (GTM) that actually works

### Channel Strategy

**Primary Channels:**
1. **Content (SEO + LinkedIn):** Articles on "agency productivity", "Slack task management"
2. **Outbound (Email):** Targeted list of 500 agencies in Malaysia/Singapore

**Secondary Channel:**
3. **Partnerships:** Slack app directory, agency communities (e.g., ShopTalk, Agency Stack)

**Why These:**
- Agencies Google their problems (SEO captures intent)
- Founders active on LinkedIn (thought leadership)
- Direct outreach works for B2B (500 is doable for 1 person)

### Acquisition Loops

**Content Loop:**
```
Write article (agency pain) → Rank on Google → Trial signup →
User shares with team → More trials → User stories → New content
```

**Referral Loop:**
```
User loves product → Invite 3 teammates → Team adopts →
Refer to peer agency → Earn 1 month free → More referrals
```

**Outbound Loop:**
```
Build list (agencies 5-15 people) → Personalized cold email →
Book demo → Trial signup → Convert to paid → Ask for intro
```

**Partnership Loop:**
```
List on Slack app directory → Agencies discover → Install →
Good reviews → Higher ranking → More installs
```

### Sales Motion

**Primary: Self-Serve**
- Signup → connect Slack → see tasks auto-captured → upgrade

**Assisted (for 10+ user accounts):**
1. Demo request form
2. Biz founder sends personal email (not automated)
3. 20-min Zoom demo (show real Slack integration)
4. Send trial invite + custom onboarding doc
5. Check-in on day 3, day 7
6. Close on day 14 or lose

**Scripts:**

**Cold Email (Outbound):**
```
Subject: Spending 2+ hours/day chasing task status?

Hi [Name],

I noticed [Agency Name] uses Slack for client work. Quick question:

How much time does your team spend asking "what's the status of X?" 
across Slack, Trello, email, spreadsheets?

We built TaskFlow AI to solve this exact problem for agencies like yours:
→ Auto-captures tasks from Slack (no behavior change)
→ Predicts blockers 48hrs before deadlines
→ One source of truth for your team

We're offering 10 Malaysian agencies a free 30-day trial + setup help.

Interested? Just reply "yes" and I'll send you access.

Best,
[Founder Name]
TaskFlow AI
```

**Objection Handling:**

| Objection | Response |
|-----------|----------|
| "Too expensive" | "Compared to what? Asana is $220 MYR/user/mo when converted. We're $99. Plus you save 2 hours/week = $X salary cost." |
| "We already use [tool]" | "Great! TaskFlow works alongside [tool]. You keep using it, we just auto-capture tasks from Slack so nothing falls through cracks." |
| "Not sure we need this" | "Fair. What if I show you live, using your actual Slack? 15-min demo, you'll know if it's valuable." |
| "Will try later" | "Totally understand. Can I send you a 1-week trial link? No credit card, just connect Slack and see if it helps." |

### Onboarding Flow (Time-to-Value: <10 minutes)

1. **Signup** (1 min): Email + password
2. **Connect Slack** (2 min): OAuth flow
3. **Choose channels** (1 min): Select 2-3 channels to monitor
4. **See AI tasks** (5 min): AI immediately shows tasks extracted from last 24 hours
5. **Aha moment:** "Wow, it found 12 tasks I forgot about"

**Metrics:**
- Time to first AI task: <5 minutes
- Tasks captured in first session: 5+ (goal)

### Retention Plan

**Habit Hooks:**
- Daily digest (consistent time, e.g., 9am)
- Slack notifications for blockers (creates urgency)
- Weekly summary (show time saved)

**Success Check-Ins:**
- Day 7: "How's it going?" email
- Day 30: "You've saved X hours!" email + NPS survey
- Day 60: Offer to add more integrations
- Day 90: "Upgrade to annual?" (15% discount)

**Lifecycle Messaging:**

| Trigger | Message | Goal |
|---------|---------|------|
| **No login 7 days** | "Miss us? Here's what's new" | Re-engage |
| **High usage** | "Invite your team, get 1 month free" | Expansion |
| **Low usage** | "Need help setting up? Book a call" | Support |
| **Downgrade** | "What changed? Can we help?" | Win-back |

**Next Actions:**
- [ ] Write 10 LinkedIn posts (agency productivity)
- [ ] Build list of 500 agencies (LinkedIn Sales Navigator)
- [ ] Create cold email sequence (3 emails)
- [ ] Set up Slack app directory listing
- [ ] Build onboarding flow in product
- [ ] Configure lifecycle emails in SendGrid

---

## F) Financial Model (simple but real)

### Cost Structure

**Fixed Costs (Monthly):**
- Infrastructure (DigitalOcean, Vercel): MYR 200
- SaaS tools (Slack, SendGrid, Stripe, Pinecone): MYR 300
- OpenAI API: MYR 500 (assumption: 1,000 tasks/day)
- Domain, misc: MYR 100
- **Total Fixed:** MYR 1,100/mo

**Variable Costs (per customer):**
- OpenAI API: ~MYR 10/user/mo (task extraction + embeddings)
- Infrastructure (storage, compute): MYR 5/user/mo
- **Total Variable:** MYR 15/user/mo

**Biggest Drivers:**
- OpenAI API costs (80% of variable)
- Founder time (not counted but opportunity cost)

### Unit Economics

**Assumptions:**
- Average customer: 8 users (midpoint of 5-15 ICP)
- Tier mix: 10% Starter, 70% Pro, 20% Agency
- Churn: 10% monthly (assumption, high for initial phase)

**CAC (Customer Acquisition Cost):**
- Content: ~MYR 0 (organic, founder time)
- Outbound: MYR 100/customer (tools + time)
- **Blended CAC:** MYR 50/customer

**LTV (Lifetime Value):**
- ARPU (average revenue per user): (0.1×49 + 0.7×99 + 0.2×249) = MYR 119/user/mo
- Per customer (8 users): MYR 952/mo
- Lifetime (1/churn): 10 months
- **LTV:** MYR 9,520/customer

**Gross Margin:**
- Revenue per customer/mo: MYR 952
- Variable cost per customer/mo: 8 users × MYR 15 = MYR 120
- **Gross margin:** (952-120)/952 = 87%

**LTV:CAC Ratio:** 9,520/50 = 190:1 (amazing, but assumes low CAC from content/outbound)

**Assumption:** CAC will increase as we scale (paid ads, partnerships)

### 90-Day Revenue Plan

| Week | Target | Leading Indicator | Cumulative MRR |
|------|--------|-------------------|----------------|
| **1-2** | 0 customers | 20 email signups | MYR 0 |
| **3-4** | 2 pilot customers | 5 demo calls | MYR 1,600 |
| **5-6** | 3 more customers | 10 trials started | MYR 4,400 |
| **7-8** | 3 more customers | 15 trials, 5 conversions | MYR 7,200 |
| **9-10** | 4 more customers | 20 trials, 8 conversions | MYR 11,000 |
| **11-12** | 3 more customers | 25 trials, 12 conversions | MYR 14,000 |
| **13** | Review + adjust | 30 total trials | MYR 14,000 |

**Targets by Day 90:**
- 15 paying customers
- MYR 14,000 MRR (monthly recurring revenue)
- 30 trials started
- 50% trial-to-paid conversion

**Leading Indicators:**
- Email list growth: 50/week
- Demo requests: 2/week
- Trials started: 3/week
- Trial-to-paid: 50%+

### Pricing Sensitivity Notes

**When to Raise Prices:**
- **Trigger 1:** Trial-to-paid conversion >70% for 2 consecutive months
- **Trigger 2:** Churn <5% for 3 consecutive months
- **Trigger 3:** 50+ customers with 6+ month wait-list

**How to Raise:**
- Grandfather existing customers
- Raise new customer prices by 20%
- Test new tier (e.g., "Enterprise")

**When to Lower Prices:**
- Trial-to-paid <30% for 3 consecutive months
- Customer feedback: "too expensive" is top objection

**Next Actions:**
- [ ] Set up financial model spreadsheet
- [ ] Track costs weekly (OpenAI, infrastructure)
- [ ] Monitor LTV:CAC monthly
- [ ] Create pricing sensitivity dashboard
- [ ] Review targets every Friday

---

## G) Build Plan (90 days)

### Phase 1: Foundations (Week 0-2)

**Outcomes:**
- Dev environment set up
- CI/CD pipeline working
- Basic auth + Slack OAuth functional
- Landing page live

**Tasks:**
| Task | Owner | DoD |
|------|-------|-----|
| Set up repo, Docker, .env | Tech | Can run locally |
| Configure DigitalOcean (Postgres, Redis, app) | Tech | Can deploy |
| Build auth (email/password) | Tech | User can signup/login |
| Slack OAuth integration | Tech | Can connect Slack workspace |
| Landing page (Next.js) | Tech | Live at taskflowai.com |
| Stripe test mode setup | Tech | Can create subscription |

**Definition of Done:**
- User can signup, login, connect Slack workspace
- Landing page deployed
- CI/CD: Push to main → auto-deploy to staging

---

### Phase 2: MVP Build + Pilot (Week 3-6)

**Outcomes:**
- AI task extraction working
- Task list view functional
- 2 pilot customers using product
- Daily email digest sending

**Tasks:**
| Task | Owner | DoD |
|------|-------|-----|
| Slack webhook listener | Tech | Receives all channel messages |
| OpenAI task extraction (prompt + API) | Tech | 80%+ accuracy on test set |
| Task CRUD API + DB schema | Tech | Can create/read/update tasks |
| Task list page (React) | Tech | Shows all tasks, filter by status |
| Email digest cron job | Tech | Sends daily at 9am |
| Onboarding flow (connect Slack) | Tech | <10 min to first AI task |
| Recruit 2 pilot customers | Biz | Signed pilot agreement |
| Support workflow (email → Slack) | Biz | Can respond to pilots <1hr |

**Definition of Done:**
- 2 pilot customers using product daily
- AI extracts 10+ tasks/day per customer
- Daily digest sending reliably
- Zero critical bugs

---

### Phase 3: Launch + Iterate (Week 7-10)

**Outcomes:**
- Public launch
- 10+ paying customers
- Blocker prediction live
- Trial-to-paid funnel optimized

**Tasks:**
| Task | Owner | DoD |
|------|-------|-----|
| Blocker prediction (v1: heuristics) | Tech | Flags 5+ blockers/day |
| Team view (workload by person) | Tech | Shows task distribution |
| Billing integration (Stripe live mode) | Tech | Can charge customers |
| Trial expiration + upgrade flow | Tech | Trial ends → prompts upgrade |
| SEO content (10 articles) | Biz | Published on blog, indexed |
| Outbound email (500 agencies) | Biz | 50 demo requests |
| Launch on Slack app directory | Biz | Listed + 5 reviews |
| Customer feedback loop (NPS survey) | Biz | Survey sent day 7, 30 |

**Definition of Done:**
- 10 paying customers
- MYR 8,000+ MRR
- Blocker prediction accuracy >60%
- Trial-to-paid >40%

---

### Phase 4: Scale Levers (Week 11-13)

**Outcomes:**
- 15+ paying customers
- Content flywheel spinning (SEO traffic growing)
- Referral program launched
- V2 roadmap prioritized

**Tasks:**
| Task | Owner | DoD |
|------|-------|-----|
| Referral program (invite 3, get 1mo free) | Tech | Tracking + payouts working |
| Analytics dashboard (MRR, churn, usage) | Tech | Daily review |
| Email integration (Gmail, basic) | Tech | Can extract tasks from email |
| Advanced filters (by project, tag, date) | Tech | Users can filter easily |
| SEO growth (backlinks, guest posts) | Biz | 5 backlinks acquired |
| Partnership outreach (agency communities) | Biz | 2 partnerships live |
| Customer case study (1 deep story) | Biz | Published on site + LinkedIn |
| V2 roadmap (based on feedback) | Both | Top 10 features prioritized |

**Definition of Done:**
- 15 paying customers
- MYR 14,000+ MRR
- Referral program: 3+ referrals
- SEO: 100+ organic visits/week

---

## H) Tech Execution Pack

### Repo Structure

```
taskflow-ai/
├── apps/
│   ├── web/                 # Next.js frontend
│   ├── api/                 # FastAPI backend
│   └── workers/             # Background jobs (Celery)
├── packages/
│   ├── db/                  # Database models, migrations
│   ├── ai/                  # OpenAI, embeddings, RAG
│   └── integrations/        # Slack, Gmail, Stripe
├── infra/
│   ├── docker-compose.yml   # Local dev
│   ├── terraform/           # DigitalOcean resources
│   └── k8s/ (future)        # Kubernetes (if needed)
├── scripts/
│   └── seed.py              # Seed test data
└── tests/
    ├── unit/
    ├── integration/
    └── e2e/
```

### API List

**Auth:**
- `POST /api/auth/signup` - Create account
- `POST /api/auth/login` - Login
- `POST /api/auth/logout` - Logout
- `GET /api/auth/me` - Get current user

**Integrations:**
- `GET /api/integrations/slack/oauth` - Start Slack OAuth
- `POST /api/integrations/slack/webhook` - Slack event webhook
- `GET /api/integrations/gmail/oauth` - Start Gmail OAuth

**Tasks:**
- `GET /api/tasks` - List tasks (filter by status, assignee, project)
- `POST /api/tasks` - Create task (manual)
- `GET /api/tasks/:id` - Get task details
- `PATCH /api/tasks/:id` - Update task
- `DELETE /api/tasks/:id` - Archive task (soft delete)

**AI:**
- `POST /api/ai/extract` - Extract task from text (internal)
- `GET /api/ai/blockers` - Get predicted blockers

**Billing:**
- `GET /api/billing/subscription` - Current subscription
- `POST /api/billing/checkout` - Create checkout session
- `POST /api/billing/webhook` - Stripe webhook

### DB Schema Outline

**Users:**
- id, email, password_hash, created_at, updated_at

**Companies:**
- id, name, subscription_tier, created_at

**UserCompanyMembership:**
- user_id, company_id, role (owner/admin/member)

**Integrations:**
- id, company_id, type (slack/gmail), credentials_encrypted, created_at

**Tasks:**
- id, company_id, title, description, assignee_id, status, deadline, source (ai/manual), confidence_score, created_at

**Predictions:**
- id, task_id, type (blocker), confidence, reason, created_at

**Events:**
- id, company_id, type, payload, created_at (for audit log)

### Event Model

**Task Created:**
```json
{
  "event": "task.created",
  "task_id": "123",
  "source": "ai",
  "confidence": 0.85
}
```

**Task Completed:**
```json
{
  "event": "task.completed",
  "task_id": "123",
  "completed_by": "user_456",
  "time_to_complete": "2 days"
}
```

**Blocker Predicted:**
```json
{
  "event": "blocker.predicted",
  "task_id": "123",
  "reason": "No activity in 3 days, deadline in 2 days"
}
```

### Observability

**Logs:**
- Structured JSON logs (timestamp, level, message, context)
- Tools: DigitalOcean managed logging or Logtail

**Metrics:**
- API response times (p50, p95, p99)
- Task extraction accuracy (accepted vs rejected)
- Background job queue depth
- Tools: Prometheus + Grafana (or DigitalOcean metrics)

**Traces:**
- Track API request → DB query → OpenAI call
- Tools: OpenTelemetry + Jaeger (optional, defer to V2)

**Alert Rules:**
- API error rate >5% for 5 min → alert founder
- OpenAI API failure >3 consecutive attempts → alert
- Database connection pool exhausted → alert
- Stripe webhook failures → alert

### Security

**Auth:**
- JWT tokens (access token: 1 hour, refresh token: 30 days)
- Password hashing: bcrypt (cost factor 12)

**RBAC:**
- Roles: Owner (all permissions), Admin (manage team), Member (read/write tasks)
- Row-level security: Users can only access tasks in their company

**Secrets:**
- Environment variables (not in code)
- DigitalOcean App Platform secrets manager
- Rotate API keys every 90 days

**PII Handling:**
- Encrypt Slack/Gmail credentials at rest (AES-256)
- No PII in logs (mask emails, names)
- GDPR: Data export + deletion API

**Audit Logs:**
- Log all task creates/updates/deletes
- Log all billing events
- Retention: 1 year

### Deployment

**Environments:**
- Local: Docker Compose
- Staging: DigitalOcean App Platform (auto-deploy on push to `staging` branch)
- Production: DigitalOcean App Platform (manual deploy from `main` branch)

**CI/CD Steps:**
1. Push to branch
2. Run tests (pytest, jest)
3. Lint (black, eslint)
4. Build Docker images
5. Deploy to environment
6. Run smoke tests
7. Notify Slack

**Rollback Strategy:**
- Keep last 3 deploys in DigitalOcean
- Rollback via DigitalOcean UI (1-click)
- If DB migration broke: Revert migration, restore DB backup (daily backups)

### Backlog (Top 20 Tickets)

| # | Title | Acceptance Criteria | Priority | Estimate |
|---|-------|---------------------|----------|----------|
| 1 | User signup/login | User can create account, login, logout | P0 | 2d |
| 2 | Slack OAuth integration | User can connect Slack workspace | P0 | 3d |
| 3 | Slack webhook listener | Receive + parse Slack messages | P0 | 2d |
| 4 | OpenAI task extraction | Extract task from text with 80%+ accuracy | P0 | 3d |
| 5 | Task CRUD API | Create, read, update, archive tasks | P0 | 2d |
| 6 | Task list page | Display all tasks, filter, sort | P0 | 3d |
| 7 | Daily email digest | Send digest at 9am daily | P1 | 2d |
| 8 | Stripe billing integration | Charge customers, manage subscriptions | P0 | 3d |
| 9 | Trial expiration flow | Prompt upgrade when trial ends | P1 | 1d |
| 10 | Blocker prediction v1 | Heuristics: overdue, no activity | P1 | 2d |
| 11 | Team workload view | Show tasks by assignee | P1 | 2d |
| 12 | Gmail integration | Extract tasks from emails | P2 | 4d |
| 13 | Referral program | Invite 3 friends → 1 month free | P2 | 3d |
| 14 | Analytics dashboard | MRR, churn, usage metrics | P2 | 2d |
| 15 | Advanced task filters | Filter by project, tag, date range | P2 | 2d |
| 16 | Mobile-responsive design | Works on mobile browsers | P1 | 2d |
| 17 | Onboarding tooltips | Guide user through first session | P2 | 1d |
| 18 | Customer NPS survey | Auto-send on day 7, 30 | P2 | 1d |
| 19 | Audit logs | Log all task/billing events | P1 | 2d |
| 20 | Data export (GDPR) | User can download all their data | P2 | 2d |

**Next Actions:**
- [ ] Create GitHub repo with structure above
- [ ] Set up DigitalOcean account + resources
- [ ] Configure CI/CD pipeline
- [ ] Create database schema + migrations
- [ ] Build backlog in GitHub Issues
- [ ] Assign priorities + estimates

---

## I) Automation Stack (AI-native ops)

### Suggested Tools by Function

| Function | Tool | Why |
|----------|------|-----|
| **CRM** | HubSpot (free tier) | Track leads, deals, email sequences |
| **Support** | Intercom or plain email → Slack | Simple for <50 customers |
| **Billing** | Stripe | Standard for SaaS, handles subscriptions |
| **Analytics** | Mixpanel (free tier) | Track user behavior, funnels |
| **Knowledge Base** | Notion | Docs, SOPs, internal wiki |
| **Email** | SendGrid | Transactional + marketing emails |
| **Monitoring** | Sentry | Error tracking |
| **Uptime** | UptimeRobot (free) | Ping every 5 min |

### 5 Automations to Implement First

| # | Automation | Trigger | Action | Owner |
|---|------------|---------|--------|-------|
| 1 | **Trial expiration reminder** | Trial ends in 3 days | Email: "Upgrade now, get 20% off first month" | Tech |
| 2 | **Blocker notification** | AI predicts blocker | Slack DM to assignee + task owner | Tech |
| 3 | **Inactive user re-engagement** | No login for 7 days | Email: "We miss you! Here's what's new" | Biz |
| 4 | **New customer onboarding** | Slack connected | Email: "3 steps to get the most from TaskFlow" | Biz |
| 5 | **Support ticket routing** | Email to support@ | Create Slack thread, notify biz founder | Biz |

### Agent Permissions Matrix

| Agent | Can Do | Requires Approval |
|-------|--------|-------------------|
| **Task Extractor** | Read Slack messages, create draft tasks | Human approves draft (first 30 days) |
| **Blocker Predictor** | Flag tasks, send Slack DM | None (if accuracy >80%) |
| **Digest Generator** | Read tasks, send email digest | None (users can opt out) |
| **Support Bot** | Answer FAQ from docs | Escalate to human for billing/bugs |
| **Sales Assistant** | Send follow-up emails, book demos | Human reviews email before sending (first 90 days) |

**Approval Gates:**
- Any email to >10 people: Human approval
- Any refund >MYR 500: Human approval
- Any task deletion: Human approval (AI can only archive)
- Any pricing change: Human approval

**Next Actions:**
- [ ] Set up HubSpot + Stripe + SendGrid
- [ ] Configure 5 automations above
- [ ] Create permissions matrix in code (RBAC)
- [ ] Test approval gates
- [ ] Document agent behaviors in Notion

---

## J) Risk Register

| # | Risk | Impact | Mitigation | Early Warning Signal | Owner |
|---|------|--------|------------|----------------------|-------|
| 1 | **OpenAI API costs spike** | High (blow budget) | Set hard quota limits, monitor daily | Cost >MYR 500/day | Tech |
| 2 | **Low trial-to-paid conversion** | High (no revenue) | Improve onboarding, add support calls | <30% for 2 weeks | Biz |
| 3 | **AI extracts wrong tasks (accuracy)** | Medium (user trust) | Human review loop, confidence threshold | Accuracy <70% | Tech |
| 4 | **Slack API rate limits** | Medium (features break) | Implement caching, batch requests | 429 errors >5/hour | Tech |
| 5 | **Competitor launches similar product** | High (market share) | Move fast, build moat (integrations, data) | Competitor mentioned in calls | Biz |
| 6 | **Data breach / security incident** | Critical (trust, legal) | Regular audits, penetration testing | Unauthorized access attempts | Tech |
| 7 | **Founder burnout** | High (project stops) | Set boundaries, weekly retros, delegate | 60+ hour weeks for 4 weeks | Both |
| 8 | **Customer churn >15%/month** | High (no growth) | Improve retention, check-ins, NPS | Churn >10% for 2 months | Biz |
| 9 | **Compliance issue (GDPR, privacy)** | High (fines, reputation) | Legal review, data policies, audit logs | Customer complaint about data | Biz |
| 10 | **Wrong ICP (agencies don't adopt)** | Critical (pivot needed) | Pilot early, iterate fast | <50% pilots convert | Both |

**Next Actions:**
- [ ] Set up risk review (monthly)
- [ ] Monitor early warning signals weekly
- [ ] Assign risk owners
- [ ] Create mitigation playbooks
- [ ] Add risks to weekly retro agenda

---

## Diagrams (ASCII)

### 1. System Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                         User (Browser)                          │
└────────────────┬────────────────────────────────────────────────┘
                 │
                 v
┌─────────────────────────────────────────────────────────────────┐
│                    Next.js Frontend (Vercel)                    │
│  - Landing page  - Task list  - Settings  - Billing            │
└────────────────┬────────────────────────────────────────────────┘
                 │
                 v
┌─────────────────────────────────────────────────────────────────┐
│                FastAPI Backend (DigitalOcean)                   │
│  - Auth API  - Task CRUD  - AI API  - Billing API              │
└─────┬───────────┬───────────┬───────────┬───────────┬──────────┘
      │           │           │           │           │
      v           v           v           v           v
   ┌────┐    ┌────────┐  ┌────────┐  ┌────────┐  ┌────────┐
   │ DB │    │ Redis  │  │ OpenAI │  │ Slack  │  │ Stripe │
   │(PG)│    │(cache) │  │  API   │  │  API   │  │  API   │
   └────┘    └────────┘  └────────┘  └────────┘  └────────┘
      │           │           │           │           │
      v           v           v           v           v
   ┌─────────────────────────────────────────────────────────┐
   │           Background Workers (Celery)                   │
   │  - Slack webhook processor  - Task extractor            │
   │  - Blocker predictor  - Digest generator                │
   └─────────────────────────────────────────────────────────┘
```

### 2. GTM Loop

```
┌──────────────────────────────────────────────────────────────┐
│                     Content Marketing                         │
│  Write blog post on "Slack task management"                  │
└────────────┬─────────────────────────────────────────────────┘
             │
             v
┌────────────────────────────────────────────────────────────┐
│                        SEO Traffic                         │
│  Rank on Google → Agency founder searches problem         │
└────────────┬───────────────────────────────────────────────┘
             │
             v
┌────────────────────────────────────────────────────────────┐
│                      Trial Signup                          │
│  Founder signs up → connects Slack → sees AI tasks        │
└────────────┬───────────────────────────────────────────────┘
             │
             v
┌────────────────────────────────────────────────────────────┐
│                      Conversion                            │
│  Trial → paid (50% conversion rate)                        │
└────────────┬───────────────────────────────────────────────┘
             │
             v
┌────────────────────────────────────────────────────────────┐
│                      Expansion                             │
│  Invite team (3-5 users) → refer peer agency               │
└────────────┬───────────────────────────────────────────────┘
             │
             v
┌────────────────────────────────────────────────────────────┐
│                    User Stories                            │
│  Customer case study → LinkedIn post → more SEO backlinks  │
└────────────┬───────────────────────────────────────────────┘
             │
             └──────> (Loop back to Content Marketing)
```

### 3. Data/Eval Loop

```
┌──────────────────────────────────────────────────────────────┐
│                   Data Collection                            │
│  Slack messages, emails, manual tasks                        │
└────────────┬─────────────────────────────────────────────────┘
             │
             v
┌────────────────────────────────────────────────────────────┐
│                   AI Task Extraction                       │
│  OpenAI prompt → extract title, assignee, deadline         │
└────────────┬───────────────────────────────────────────────┘
             │
             v
┌────────────────────────────────────────────────────────────┐
│                  Confidence Scoring                        │
│  If >70% confidence → create draft task                    │
│  If <70% → discard (log for review)                        │
└────────────┬───────────────────────────────────────────────┘
             │
             v
┌────────────────────────────────────────────────────────────┐
│                    Human Review                            │
│  User accepts/edits/deletes AI task → feedback signal      │
└────────────┬───────────────────────────────────────────────┘
             │
             v
┌────────────────────────────────────────────────────────────┐
│                   Evaluation Metrics                       │
│  Precision, recall, user acceptance rate                   │
└────────────┬───────────────────────────────────────────────┘
             │
             v
┌────────────────────────────────────────────────────────────┐
│                   Model Improvement                        │
│  Weekly: Review 100 tasks, adjust prompt/threshold         │
│  Monthly: Retrain if needed, update guardrails             │
└────────────┬───────────────────────────────────────────────┘
             │
             └──────> (Loop back to Data Collection)
```

---

## Day-1 Checklist

**Week 0 (Setup):**
- [ ] Register domain: taskflowai.com
- [ ] Set up GitHub repo (private)
- [ ] Create DigitalOcean account + project
- [ ] Set up Stripe account (test mode)
- [ ] Configure SendGrid for emails
- [ ] Create Slack app + get API credentials
- [ ] Set up OpenAI API account + billing
- [ ] Create Notion workspace (docs, SOPs, roadmap)
- [ ] Set up local dev environment (Docker)
- [ ] Deploy "coming soon" landing page

**Week 1 (Foundations):**
- [ ] Build user signup/login (email + password)
- [ ] Build Slack OAuth integration
- [ ] Connect Slack workspace (test)
- [ ] Set up database (Postgres on DigitalOcean)
- [ ] Create CI/CD pipeline (GitHub Actions → DigitalOcean)
- [ ] Write first blog post ("5 Signs Your Agency Needs TaskFlow AI")

**Week 2 (MVP Core):**
- [ ] Build Slack webhook listener
- [ ] Implement OpenAI task extraction (v1)
- [ ] Create task CRUD API
- [ ] Build task list page (Next.js)
- [ ] Test with own Slack workspace (dogfood)
- [ ] Recruit 2 pilot customers (agencies you know)

**Week 3-4 (Pilot):**
- [ ] Onboard 2 pilot customers
- [ ] Daily check-ins with pilots
- [ ] Fix critical bugs
- [ ] Build email digest (daily summary)
- [ ] Improve task extraction based on feedback
- [ ] Write 3 more blog posts (SEO)

**Week 5-6 (Launch Prep):**
- [ ] Integrate Stripe billing (live mode)
- [ ] Build trial expiration + upgrade flow
- [ ] Implement blocker prediction (v1)
- [ ] Test end-to-end flow (signup → trial → paid)
- [ ] Create launch content (Product Hunt, LinkedIn)
- [ ] Build list of 500 agencies for outreach

**Week 7 (Public Launch):**
- [ ] Launch on Product Hunt
- [ ] Post on LinkedIn (founders + company page)
- [ ] List on Slack app directory
- [ ] Send first outbound email batch (100 agencies)
- [ ] Monitor signups, conversions, bugs
- [ ] Customer support (respond <1hr)

**Week 8+ (Growth):**
- [ ] Iterate based on customer feedback
- [ ] Send weekly outbound batches
- [ ] Publish weekly blog posts
- [ ] Build referral program
- [ ] Track towards 15 customers by week 12

---

## First 10 Customers Plan

### Customer #1-2: Pilot Customers (Week 2-4)

**Source:** Personal network (agencies you know)

**Approach:**
- Personal email: "Hey [name], I'm building a tool to solve [problem]. Want to try it free for 30 days?"
- Offer 1:1 onboarding call
- Ask for weekly feedback

**Goal:** Validate product-market fit, fix critical bugs

---

### Customer #3-5: Early Adopters (Week 5-7)

**Source:** LinkedIn outreach + blog SEO

**Approach:**
- LinkedIn DM: "Saw you run [agency]. Are you struggling with [problem]?"
- Offer free trial + setup help
- Ask for testimonial if they love it

**Goal:** Prove value prop, get testimonials

---

### Customer #6-10: Launch Momentum (Week 8-10)

**Source:** Product Hunt, Slack app directory, cold email

**Approach:**
- Product Hunt launch (build buzz)
- List on Slack app directory (passive installs)
- Cold email 100 agencies/week

**Goal:** Hit 10 paying customers, MRR >MYR 8,000

---

### Customer #11-15: Scale (Week 11-13)

**Source:** Referrals, content, partnerships

**Approach:**
- Referral program: Existing customers refer peers
- SEO: Blog posts start ranking, organic signups
- Partnerships: Agency communities, Slack partner program

**Goal:** 15 paying customers, MRR >MYR 14,000

---

### Ideal First Customer Profile

- **Agency size:** 5-10 people (not too small, not too big)
- **Tech-savvy:** Already using Slack, comfortable with SaaS tools
- **Pain level:** High (missed deadlines, task chaos)
- **Budget:** Can afford MYR 500-1000/month
- **Responsive:** Quick to give feedback, iterate with you

**How to Find Them:**
- LinkedIn search: "agency founder" + "Malaysia" + "Slack"
- Slack communities: Search for agencies in directories
- Referrals: Ask pilot customers who they know
- Events: Join agency meetups, Facebook groups

---

## Success Criteria (Know When You've Won)

**By Day 90:**
- [ ] 15+ paying customers
- [ ] MYR 14,000+ MRR
- [ ] Trial-to-paid conversion >40%
- [ ] Monthly churn <10%
- [ ] NPS >40
- [ ] Product works reliably (uptime >99%)
- [ ] Founder not burned out (working <50 hrs/week)

**Qualitative Signals:**
- Customers say "I can't live without this"
- Referrals happen organically
- Competitors notice you
- Inbound demo requests (not just outbound)
- Team asks "when can we add [feature]?"

---

**End of Blueprint**

*Ready to build? Start with the Day-1 Checklist. Review the First 10 Customers Plan. Execute one week at a time. Measure everything. Iterate fast. Ship daily.*

**Questions? Need help? DM the founders on LinkedIn or email: hello@taskflowai.com**
