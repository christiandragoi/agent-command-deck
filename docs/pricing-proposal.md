# Pricing Proposal — Agent Command Deck

## Pricing Philosophy

**Value-based, not cost-plus.** Price is set by the time and money Agent Command Deck saves for a recruiting team — not by our infrastructure costs.

- A recruiter spends ~23h/week on CV screening. At $45/h fully loaded, that's $1,035/week or ~$4,140/month per recruiter.
- If Agent Command Deck cuts that by 80%, it saves ~$3,312/month per recruiter.
- Our pricing captures a fraction of that value: **$99–$299+/mo.**

## Tier Comparison

| Feature | Starter | Growth | Enterprise |
|---------|---------|--------|------------|
| **Price** | $99/mo | $299/mo | Custom |
| **CVs processed per month** | 100 | 500 | Unlimited |
| **AI scoring against job reqs** | Basic match % | Advanced scoring w/ skill gap analysis | Full custom scoring models |
| **AI triage / ranking** | Manual sort | Auto-ranked board | Custom ranking algorithms |
| **User seats** | 1 | 5 | Unlimited |
| **API access** | — | REST API (rate-limited) | Full API access |
| **ATS integrations** | CSV export | Greenhouse, Lever, Ashby | All integrations + custom |
| **SSO / SAML** | — | — | Included |
| **Dedicated support** | Email (48h) | Email + chat (8h) | Slack + phone (1h SLA) |
| **Custom scoring rubrics** | — | — | Included |
| **Target audience** | Solo recruiters, small teams | Growing TA departments | Enterprise / staffing agencies |

## Annual vs. Monthly Pricing

| Tier | Monthly | Annual (billed yearly) | Effective Annual Savings |
|------|---------|----------------------|--------------------------|
| Starter | $99/mo | $990/yr ($82.50/mo) | 2 months free |
| Growth | $299/mo | $2,990/yr ($249.17/mo) | 2 months free |
| Enterprise | Custom | Custom (annual commit) | Negotiable |

## Pilot Discount

**First 10 pilot customers: 50% off for 3 months.**
- Starter: $49.50/mo (normally $99)
- Growth: $149.50/mo (normally $299)
- Pilot includes: weekly check-in call, priority feedback channel, case study opportunity

## Stripe Product Structure

### Products

| Product ID (Stripe) | Name | Type |
|---------------------|------|------|
| `starter_monthly` | Agent Command Deck — Starter | Service |
| `starter_annual` | Agent Command Deck — Starter (Annual) | Service |
| `growth_monthly` | Agent Command Deck — Growth | Service |
| `growth_annual` | Agent Command Deck — Growth (Annual) | Service |

### Prices (Stripe)

| Product | Amount | Interval | Currency |
|---------|--------|----------|----------|
| Starter Monthly | $99 | month | USD |
| Starter Annual | $990 | year | USD |
| Growth Monthly | $299 | month | USD |
| Growth Annual | $2,990 | year | USD |

### Metered Billing (Future)
For Enterprise plans, consider metered billing at $0.50 per CV processed beyond the base allocation, capped at $500/mo overage maximum.
