# Workflow to Productize — Candidate Intake & AI Triage

## Primary Workflow
Agent Command Deck's core productized workflow is **Candidate Intake & AI Triage** — the end-to-end pipeline from receiving a CV to having a recruiter-approved shortlist ready for outreach.

### Workflow Steps
1. **CV Received** (email forward, file upload, ATS webhook, API push)
2. **CV Parsed & Normalized** (name, contact, skills, experience, education, work history)
3. **AI Scores Against Job Req** (match %, missing skills, experience level, overall ranking)
4. **Recruiter Reviews Ranked Candidates** (Kanban: High/Medium/Low, click for detail)
5. **Recruiter Approves Top Candidates** (one-click approve, reject with reason, move to next stage)
6. **Auto-Outreach or Export to ATS** (generate InMail/email, push to ATS record)

### Technical Stack
| Step | Component | Technology |
|------|-----------|------------|
| CV intake | Email parser, file upload, webhook | Python FastAPI + Resend |
| CV parsing | LLM-based extraction (structured JSON) | GPT-4o / Claude 3.5 |
| AI scoring | Prompt-based scoring against requirements | LLM with Rubric prompt |
| Kanban board | Drag-and-drop real-time UI | Next.js + dnd-kit |
| Approve action | One-click state transition | Optimistic UI |
| Auto-outreach | Template + AI personalization | LLM generates message |

### Scoring Rubric (AI Prompt)
Score candidate against job description. Return JSON: match_score (0-100), skills_present[], skills_missing[], experience_years, experience_level, education_match, recommendation (Strong Yes/Yes/Maybe/No), reasoning.

## Mock Data for Demos

### 10 Sample CVs
1. **Alice Chen** — Sr Frontend Eng — React, TS, CSS, Next.js — 6yr — 92%
2. **Bob Martinez** — Full Stack — React, Node, Python, Postgres — 5yr — 85%
3. **Clara Johnson** — Backend Eng — Python, Django, AWS, Redis — 7yr — 78%
4. **David Kim** — Junior Dev — JS, HTML, CSS, Git — 1yr — 45%
5. **Emma Wilson** — Eng Manager — React, Python, Team Lead — 8yr — 88%
6. **Frank Lee** — DevOps — AWS, Docker, K8s, Terraform — 6yr — 72%
7. **Grace Patel** — Data Eng — Python, SQL, Spark, Airflow — 4yr — 65%
8. **Henry Brown** — Mobile Dev — React Native, Swift, Kotlin — 5yr — 55%
9. **Isabella Garcia** — Product Designer — Figma, UX Research — 4yr — 35%
10. **James Taylor** — Staff Eng — React, Python, System Design — 10yr — 95%

### 3 Sample Job Reqs
- **Sr Frontend Engineer:** 5+yr React/TS, 3+yr CSS/Tailwind, Next.js, CI/CD
- **Full Stack Developer:** 3+yr React, 3+yr Node/Python, PostgreSQL, REST API
- **Engineering Manager:** 7+yr SWE, 2+yr managing 5+, full stack, Agile
