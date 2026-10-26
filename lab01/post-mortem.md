# Post-mortem: CampusPay wallet (fictional case from Lab-01)

## 1. Timeline and sources
Source for all events: fictional case from Lab-01 (no dates are given, so the events are in order).

| # | When | Event | Source |
|---|------|-------|--------|
| 1 | Start of semester | A university asks its IT unit to build a cashless payment app for the canteen and the library fines in one semester. | fictional case from Lab-01 |
| 2 | Start of semester | The head of finance "sponsors" the project by e-mail but never attends a review. | fictional case from Lab-01 |
| 3 | Start of semester | The lead developer acts as project manager and coder at the same time. | fictional case from Lab-01 |
| 4 | Start of semester | Success is defined as "launch in September". | fictional case from Lab-01 |
| 5 | During the build | A survey makes requirements grow from canteen payments to bus tickets and parking. | fictional case from Lab-01 |
| 6 | Before launch | No test with real card terminals is run. | fictional case from Lab-01 |
| 7 | Launch day | The terminals reject 40 % of payments and the canteen queue doubles. | fictional case from Lab-01 |
| 8 | Three days later, then five months later | The app is withdrawn after three days and relaunched five months later for the canteen only. | fictional case from Lab-01 |

## 2. Classification and organisation
Project / programme: it was started as one project (one app, one deadline in September), but the survey added bus tickets and parking, which are separate payment services with different users and terminals, so it grew into several related initiatives without being run as a programme. Structure and PM authority: the PM was the lead developer inside the IT unit, so the work sat in a functional organisation; as a coder and PM at once he had almost no authority over finance, the canteen or the card terminals, and no time to manage. Sponsor, charter, PMO: the sponsor existed only on paper (an e-mail, no reviews), there was no charter (success was one phrase) and the case mentions no PMO, so nobody could refuse the extra scope or stop the launch.

## 3. Success criteria
Stated: "launch in September".
Missing measurable criteria: a payment success rate (for example 99 % of terminal payments accepted), a response time per payment, the list of features in scope, a budget and an acceptance test with the real terminals on a named date.
Ignored dimensions (benefits, users, operations, team): benefits (shorter queues and less cash handling were never defined or measured), users (canteen staff and students took no part in a test), operations (nobody planned support, terminal set-up or reconciliation with finance) and team (one person did the management and the coding).

## 4. Process groups and knowledge areas
| Process group              | What went wrong or was skipped |
|----------------------------|--------------------------------|
| Initiating                 | No charter; the head of finance never accepted the sponsor role, so nobody could refuse the bus-ticket scope (events 2, 4). |
| Planning                   | A one-semester plan was made with no scope baseline, no test plan and no risk of terminal incompatibility identified (events 1, 6). |
| Executing                  | One person coded and managed, and the team built the new features of the survey on top of the first ones (events 3, 5). |
| Monitoring and controlling | There was no change control for the new requirements and no end-to-end test to check progress, so "on schedule" meant "not yet failed" (events 5, 6). |
| Closing                    | The app was withdrawn after three days and relaunched for the canteen only, with no sign that lessons were recorded or the real result accepted (event 8). |

Knowledge areas most responsible:
- Scope: requirements grew from the canteen to bus tickets and parking with no change control (event 5).
- Quality: no test with real card terminals, so the 40 % rejection rate was found by the users (events 6, 7).
- Stakeholder: the sponsor never attended a review and the terminals' users were not involved before launch (events 2, 7).

## 5. Ethics
Decision examined: launching on the planned day without a test on the real card terminals, so that real students' money and the canteen's service were the first test.
- Responsibility: the team owned the date but not the result; accepting a September launch as the only criterion meant they accepted a deadline over their duty to deliver working payments.
- Respect: students and canteen staff were treated as a test group, with doubled queues and rejected payments.
- Fairness: the cost of the failure fell on users, not on the team that chose to skip the test.
- Honesty: the case does not say what was reported to finance, but progress reported as "on schedule" without a single end-to-end test would have given a false picture, so the honest report was "launch date reachable, payments untested".

## 6. What our project will do differently
| # | Commitment (We will ...) | Measured by | By week | Charter line |
|---|--------------------------|-------------|---------|--------------|
| 1 | We will run the load test (20 sessions of 100 simulated students) and one live session over the real campus network before the pilot | load test report with 0 dropped sessions and p95 broadcast latency <= 500 ms | 13 | O3, O4, milestone week 13, risk 1 (campus proxy) |
| 2 | We will hold a signed charter with a named sponsor who attends the week-7 and week-13 gates | signatures on the charter and gate minutes with the sponsor present | 1 (signature), 7 and 13 (gates) | section 10 approval, milestone weeks 1, 7 and 13 |
| 3 | We will freeze scope after the week-3 baseline and treat every addition as a written change request | change log with 0 added features without the sponsor's written approval | 3 to 14 | section 3 out of scope, section 9 authority clause |
| 4 | We will report progress every week against the five success criteria, not against "on schedule" | weekly status report listing O1 to O5 with a measured value or "not measured yet" | 1 to 14 | O1 to O5, Monitoring and controlling row of the process-group table |
| 5 | We will get the data approval and hand the runbook to IT operations before the pilot | written approval from the data protection officer or registrar and a signed hand-over sheet | 13 | assumption 4, milestone week 13 and the week-13 phase gate |
