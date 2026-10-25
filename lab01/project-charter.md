# Project charter: Realtime Quiz platform

| Field    | Value                              |
|----------|------------------------------------|
| Version  | 1.0 (draft for sponsor approval)   |
| Date     | 2026-09-29                         |
| Sponsor  | Head of the IT department          |
| PM       | TODO name, supervising lecturer    |

## 1. Purpose and justification
Lecturers of the IT department spend hours every week marking quizzes by hand and get no live view of how well students understand a topic. The Realtime Quiz platform lets an instructor write multiple-choice quizzes and run live, timed sessions that students join with a 6-character code, with instant feedback, scores and a leaderboard. The benefit is less marking time, immediate feedback in class, and a department-owned tool without per-seat fees. The investment of 490 person-hours and 200 USD cash is justified, compared with doing nothing or buying a SaaS product, in `business-case.md` (Task 4), which recommends building it with a review gate at the week-7 MVP demo.

## 2. Objectives and success criteria
| #  | Objective (what will be true)                                         | Success criterion (number + week)                                              |
|----|-----------------------------------------------------------------------|--------------------------------------------------------------------------------|
| O1 | All Must features work together in one live demo to the sponsor       | 8 of 8 Must features pass a live demo run, week 7                              |
| O2 | The platform is used by real students in one live session             | Pilot with 50 students in one session, 0 blocking defects, week 14             |
| O3 | A broadcast reaches all clients quickly                               | <= 500 ms at the 95th percentile, measured in the load test (week 13) and the pilot (week 14) |
| O4 | One server instance carries the planned load                          | 20 concurrent sessions of 100 simulated participants on 2 vCPU and 2 GB RAM with 0 dropped sessions, load test passed by week 13 |
| O5 | The code base is tested and always releasable                         | Line coverage >= 80 % and CI green on 100 % of merges, checked at the week-7 and week-14 gates |

## 3. High-level scope
In scope:
- Quiz authoring with multiple-choice questions
- Live quiz session with a timer per question
- Instant feedback and scoring
- Leaderboard
- Real-time broadcast of questions and scores to all participants
- Authentication and role-based access (instructor, student, guest)
- Multiple concurrent sessions
- Analytics and reporting for instructors
- Export of results to CSV and PDF
- Responsive web interface

Out of scope:
- Native mobile applications
- Question types other than multiple choice
- Video conferencing
- LMS integration
- Multi-node scaling (one server instance only)

## 4. Milestones
| Week | Milestone                                                              | Ends process group         |
|------|------------------------------------------------------------------------|----------------------------|
| 1    | Charter approved, team formed                                          | Initiating                 |
| 3    | PM plan baselined; repository, CI and deployment skeleton running      | Planning                   |
| 5    | Accounts, security and quiz authoring done                             | Executing                  |
| 7    | MVP demo (all 8 Must features, live session, scoring, leaderboard)    | Executing                  |
| 10   | Analytics, export, notifications, media and responsive polish done     | Executing                  |
| 13   | Pilot readiness gate: load test green, data approval received, runbook handed to IT operations | Monitoring and controlling |
| 14   | Pilot with 50 students, closure                                        | Closing                    |

## 5. Budget summary
Effort:  students 4 x 14 x 8 h = 448 h; PM 14 x 3 h = 42 h; total 490 h
Cash:    hosting 4 x 25 USD = 100; domain 15; tools 60; reserve 25 (14 % of the 175 USD cash lines)
         total 200 USD

## 6. Assumptions
- Each student can spend 8 h per week and the PM 3 h per week for all 14 weeks.
- The Linode VPS at gicitc.com is available from week 1 at about 25 USD per month.
- 50 students and an instructor are available for the pilot session in week 14.
- The data protection officer or registrar approves storing student names and results by week 13.

## 7. Constraints
- Duration: 14 weeks, week 1 starts 2026-09-29; the MVP demo is fixed for week 7 and the pilot for week 14.
- Cash: hard cap of 200 USD, including hosting, domain, tools and reserve.
- Effort: 490 person-hours in total; no paid staff.
- Technical: one server instance of 2 vCPU and 2 GB RAM; no secrets in the repository.

## 8. High-level risks
- The campus proxy may block WebSocket traffic; the fallback is SockJS.
- Spring Boot 4 and Spring Security 7 are newer than most tutorials, which may slow the backend and security work.
- Could features (chat, anonymous join) may creep into the MVP and endanger the week-7 demo.

## 9. Project manager authority
The PM re-plans within the 490 h and 200 USD without approval, assigns tasks to team members, accepts or rejects deliverables, and decides how the reserve of 25 USD is used. Adding scope, moving the MVP demo or the pilot, changing the 200 USD cash cap, and spending beyond the reserve need the sponsor's written approval, which the sponsor gives or refuses within 5 working days.

## 10. Approval
Sponsor: ____________________  Date: ________
PM:      ____________________  Date: ________
