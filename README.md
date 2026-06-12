# Agent Command Deck

**Recruitment workflow automation. From CV intake to recruiter approval — one pipeline.**

Agent Command Deck is a niche-first workflow platform for talent operations and sourcing teams. It ingests CVs from any source, uses AI to parse and score candidates against job requirements, presents a ranked Kanban board for recruiter review, and automates outreach — all in one continuous pipeline.

## Repository Structure

```
/
├── README.md                    # This file
├── docs/
│   ├── positioning-strategy.md  # Market analysis & GTM
│   ├── pricing-proposal.md      # Pricing tiers & Stripe setup
│   ├── landing-page-structure.md# Full page layout spec
│   ├── stripe-implementation-plan.md
│   ├── signup-onboarding-flow.md
│   ├── workflow-to-productize.md# Core candidate intake pipeline
│   └── top-5-actions.md         # First paying users playbook
├── landing-page/
│   └── index.html               # Self-contained HTML landing page
└── implementation/              # (coming soon)
```

## Quick Start

1. Open `landing-page/index.html` in a browser to see the marketing site
2. Review `docs/positioning-strategy.md` for market positioning
3. Follow `docs/top-5-actions.md` for the immediate execution plan

## Color Scheme

The landing page is styled after a dark SaaS theme with amber accent:
- **Background:** `#100919`
- **Primary accent:** `#FFC107` (amber)
- **Purple gradient:** `#6d28d9` → `#853ACC`
- **Text:** `#FFFFFF` on dark, `#98A2B3` for muted

## Product Overview

| Feature | Starter | Growth | Enterprise |
|---------|---------|--------|------------|
| CVs/mo | 100 | 500 | Unlimited |
| AI Scoring | Basic | Advanced | Custom |
| Seats | 1 | 5 | Unlimited |
| API | — | ✓ | ✓ |
| Price | $99/mo | $299/mo | Custom |

## Target Workflow

**Candidate Intake & AI Triage:**
1. CV received (email forward, upload, ATS webhook)
2. AI parses & normalizes
3. Scores against job requirements
4. Recruiter reviews ranked Kanban board
5. Approves top candidates (one click)
6. Auto-generates outreach or exports to ATS

## License

All content © 2026 Agent Command Deck.
