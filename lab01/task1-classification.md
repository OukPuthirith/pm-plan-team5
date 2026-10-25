# Task 1: project, operation or programme?

| #  | Initiative | Temporary? | Unique? | Coordinated? | Class | Justification |
|----|------------|------------|---------|--------------|-------|---------------|
| 1  | Build the Realtime Quiz platform and pilot it with 50 students in week 14 | yes | yes | no | Project | It ends with the week-14 pilot and delivers a platform that did not exist before. |
| 2  | Run the nightly backup of the gicitc.com PostgreSQL database | no | no | no | Operation | It repeats every night with the same output and no end date; it keeps the service running. |
| 3  | Move the department's three web servers to a new Linode region before 15 December | yes | yes | no | Project | It has a fixed deadline (15 December) and a one-off result: servers running in the new region. |
| 4  | Answer helpdesk tickets within the 4-hour service level | no | no | no | Operation | It is a continuous, repeated service with a standing service level and no end date. |
| 5  | "Digital classroom": Realtime Quiz, LMS upgrade and lecture capture sharing one login and one grade export | yes | yes | yes | Programme | Three related projects whose shared login and grade export give a benefit none of them delivers alone. |
| 6  | Apply the monthly security patches to the VPS | no | no | no | Operation | It recurs every month with the same procedure and no end date. |
| 7  | Add multi-node scaling (RabbitMQ relay, Redis registry) to Realtime Quiz next semester | yes | yes | no | Project | It is funded for one semester and delivers a new capability (multi-node) the platform does not have. |
| 8  | Operate the Realtime Quiz platform after go-live: password resets, restarts, monitoring | no | no | no | Operation | It repeats daily for as long as the platform is in use, with no end date. |
| 9  | Write and publish the department's annual IT report for the dean by 31 January | yes | no | no | Operation | It recurs every year with the same format and audience; the 31 January deadline does not make the result new. |
| 10 | Replace 40 wireless access points in two buildings during the summer break | yes | yes | no | Project | It must finish within the summer break and delivers a one-off new set of access points. |

## Grey zones

- **Row 7 (multi-node scaling):** it could be seen as a maintenance release of the running platform (operation) or as a new project. It would be settled by who authorises it: if the sponsor funds it separately with its own budget and a defined end ("done" = two nodes passing a load test), it is a project; if it is absorbed into the operations team's routine work with no end, it is an operation.
- **Row 9 (annual IT report):** it is repetitive, yet each report has its own content and a hard deadline, and many departments run it as a small yearly project. It would be settled by what "done" means and whether a budget exists: if each year's report has a named owner, a budget and a new scope, treat it as a project; if the same template is simply refilled, it stays an operation.

## What our project hands over

At go-live in week 14 the Realtime Quiz project hands the running platform to IT operations (the VPS administrator of gicitc.com), who take over restarts, monitoring, backups, security patches and password resets. They need from the team a runbook, the production docker-compose file and environment-variable list, a working backup and restore job, and the monitoring and alert settings, delivered at least one week before the pilot. The lecturers who run quizzes receive a short user guide, and the team hands over the tagged source repository, the test and load-test reports and the lessons learned, so that any later project (such as multi-node scaling) starts from a documented base.
