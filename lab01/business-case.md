# Business case: live quizzes for the IT department

Figures come from `business-case.csv`; every amount there is computed with the formula written next to it.

## 1. Problem
Lecturers of the IT department mark quiz and exercise answers by hand and see how well a class understands a topic only after the lesson. Quantified with these assumptions:
- lecturers running quizzes: 10
- marking time saved per lecturer per week: 1 h
- teaching weeks per year: 30
- notional value of one hour: 10 USD (students are unpaid; used only to compare options)

The pain is 10 x 1 x 30 = 300 h per year, worth 300 x 10 = 3 000 USD per year, and the lack of live feedback in class is not priced.

## 2. Options
| Option | Description | One-off cost | Annual cost | Annual benefit |
|--------|-------------|--------------|-------------|----------------|
| A      | Do nothing: keep marking by hand | 0 | 0 | 0 |
| B      | Buy a quiz SaaS: Kahoot!+ Silver for educators, 10 licences | 0 | 958.80 USD (10 x 7.99 x 12) | 3 000 USD (300 h x 10 USD) |
| C      | Build Realtime Quiz with the charter budget | 4 975 USD (490 h x 10 USD = 4 900; domain 15; tools 60) | 300 USD (hosting 12 x 25) | 3 000 USD (300 h x 10 USD) plus 958.80 USD licence fee avoided compared with B |

SaaS price source: Kahoot! higher-education pricing page, https://kahoot.com/register/pricing-higher-ed/, accessed 2026-10-26. The Silver plan allows up to 100 participants per session, which covers the 50-student pilot. The page shows two prices per plan, 7.99 and 14.99 USD per educator per month; I used 7.99 USD because it is the lower price, assumed to be the annual-billing price, which is the harder case for building. Confirm the billing basis with the vendor before any purchase.

Option C's one-off cost counts the 490 person-hours of the team and PM at the notional 10 USD per hour; this is not cash. The cash cost of C is 200 USD, of which hosting is counted in the annual cost, and the 25 USD reserve is assumed unused.

## 3. Comparison
| Option | Net annual benefit | Payback (years) | Sensitivity (6 lecturers) |
|--------|--------------------|-----------------|---------------------------|
| B      | 3 000 - 958.80 = 2 041.20 | 0 (no one-off cost) | 1 800 - 575.28 = 1 224.72 |
| C compared with B | 3 000 + 958.80 - 300 = 3 658.80 | 4 975 / 3 658.80 = 1.36 | 1 800 + 575.28 - 300 = 2 075.28; payback 2.40 |
| C compared with doing nothing (A) | 3 000 - 300 = 2 700 | 4 975 / 2 700 = 1.84 | 1 800 - 300 = 1 500; payback 3.32 |

The sensitivity line changes one assumption, 6 lecturers instead of 10. Payback of C gets longer, from 1.36 to 2.40 years against B and from 1.84 to 3.32 years against doing nothing, so the build only pays back inside two years in the 10-lecturer case.

## 4. Benefits not priced
- Learning outcome: the team practises real project management and software engineering on a real product (capstone).
- Data ownership: student names and results stay on the department's own server instead of a vendor's.
- No per-seat or per-session limit: the platform is not tied to a plan cap such as 100 participants.
- Fit to local needs: for example PDF export that renders Khmer names, which a general SaaS may not do.

## 5. Risks per option
- A, do nothing: marking load stays at 300 h per year; students get no live feedback and the department misses the chance to show it can innovate.
- A, do nothing: the problem grows as classes grow, with no plan for it.
- B, buy SaaS: the vendor can change prices and plan limits, and student data is stored outside the department, which the data protection officer may not accept.
- B, buy SaaS: per-educator licences recur every year, and features such as the leaderboard or exports may sit in a higher plan.
- C, build: the campus proxy may block WebSocket traffic (fallback: SockJS).
- C, build: Spring Boot 4 and Spring Security 7 are newer than most tutorials, and late answers can race with the closing of a question, which could delay the week-7 MVP.
- C, build: after week 14 the students leave, so someone in IT operations must maintain the platform.

## 6. Recommendation and review gate
Build option C. With 10 lecturers it pays back in 1.36 years against buying a SaaS, and 1.84 years against doing nothing. The cash cost is only 200 USD, the department keeps its data, and the project is also the capstone learning outcome. With only 6 lecturers the payback grows to 2.40 years against B and 3.32 years against A, so the sponsor should confirm at least 8 to 10 lecturers will use it before the pilot, and treat the 10-lecturer figure as a target, not a given.

Review gate: if the week-7 MVP demo does not show all 8 Must features working live, switch to option B for next semester and treat the build as a two-semester project. The charter (`project-charter.md`, section 1) refers to this recommendation.
