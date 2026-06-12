# Stripe Implementation Plan — Agent Command Deck

## Overview
Agent Command Deck uses Stripe for subscription billing with three tiers (Starter, Growth, Enterprise). The implementation follows: Frontend Checkout → Stripe Session → Webhook → Entitlement.

## 1. Products & Prices Setup (Stripe Dashboard)

### Create Products
- **Agent Command Deck — Starter:** 100 CVs/mo, basic scoring, 1 user
- **Agent Command Deck — Growth:** 500 CVs/mo, AI triage, 5 users, API
- **Agent Command Deck — Enterprise:** Custom plan, contact sales

### Create Prices
| Product | Price Name | Amount | Interval |
|---------|-----------|--------|----------|
| Starter | Monthly | $99 | month |
| Starter | Annual | $990 | year |
| Growth | Monthly | $299 | month |
| Growth | Annual | $2,990 | year |

### Enterprise Handling
- No public price in Stripe. Use Payment Link for custom amounts or one-off invoice.

## 2. Checkout Session Flow
```
User → Click "Subscribe" → Your backend creates Stripe Checkout Session
→ User redirected to Stripe Checkout (hosted page) → Enter card details
→ Payment success → Redirect to success_url
→ Stripe webhook (checkout.session.completed) → Update DB entitlement
```

## 3. Webhook Events to Handle
- `checkout.session.completed` — Activate subscription, set plan
- `customer.subscription.updated` — Handle plan change/upgrade/downgrade
- `invoice.paid` — Extend subscription, reset usage counters
- `customer.subscription.deleted` — Downgrade to free tier

## 4. Entitlement Middleware
Check per-request: plan tier + usage limits (CV count). Return 403 with upgrade link if exceeded.

## 5. Test Mode → Live Mode
- Test card: 4242 4242 4242 4242
- Test all webhook events with Stripe CLI
- Verify database updates
- Test failed payment (4000 0000 0000 0002)
- Switch to live keys, update webhook endpoint, enable Radar
