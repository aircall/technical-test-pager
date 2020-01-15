# Aircall Technical Test - Aircall Pager

The goal of this test is to evaluate:
- your modeling and testing skills of a small business case
- your ability to pair program with someone to add new features
- your ability to present your project to an audience

# Agenda
The following test has 2 parts:
1. at home to design an implement a domain model (~1-2h)
2. on-site to add new features during a pair programming session and to present the result to some engineers (2 x 1h)

# Use case
Let's imagine we need to implement an alerting system for our production services:
- A **Service** (identified by its unique name) can `crash` and `trigger` an **Alert** containing an error message.
- A **Service** can have an **Escalation Policy** associated to it. 
- An **Escalation Policy** has several **Levels**, each containing the list of **Targets** to notify (e-mails or phone numbers).
- At a given **Level**, an **Alert** `knows` the Targets to `notify`. 
- An **Alert** `iterates` from one **Level** to another if nobody at a given **Level** handled it.
- When one of the **Target** `handles` the **Alert**, the system stops escalating it.

## 1. Homework (1.5 hours)
Implement a model and unit tests for this alerting system with the programming language and paradigm you prefer.
You don't need to implement any delivery and persistence mechanisms (no web server, no workers, no database).
This is just about pure domain modeling. Keep things simple and straighforward.

:warning: Do not fork this repo and do not submit any Pull Requests:warning:

When you're done, please create your public or private repo on GitHub and give access to:
- [hwd](https://github.com/hwd)
- [kimious](https://github.com/kimious)

Make sure that you put the instructions on how to run unit tests so that we can easily see the result.
  
## 2. Pair programming (1.5 hours / on-site)
Debrief on the model.
Implement a persistence system on top of the filesystem for Escalation Policies and Alerts
Implement 2 API endpoints: 
- `/service/:name/crash` (to trigger an escalation workflow if needed)
- `/alerts/:id/next` (to go through escalation levels)

## 3. Presentation and collective review (1 hour / on-site)
Presentation of the whole project in English to ~3 engineers.

# Questions
You can ask any questions by creating issues on your repo and tagging us.

Good luck!
