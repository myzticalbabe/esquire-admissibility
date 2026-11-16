# STEM learning guide — esquire-admissibility

Esquire Admissibility reads a record of proposed AI evidence and tests it against admissibility gates — a rules engine with a legal shape.

This guide is for teachers, mentors, club leaders, parents and students who want to
use this repository as a vehicle for real STEM learning — in particular for girls and
other groups still under-represented in computing, engineering and mathematics. It
says what the project actually teaches, how to run a session with it, and what to
remove so that nobody is excluded by accident.

## What this project teaches

**Subject areas**

- rule engines
- formal reasoning
- evidence and burden of proof
- applied logic

**Skills practised**

- turning a written rule into a check
- separating a fact from an inference
- explaining a decision to someone who disagrees

## Prerequisites

Python 3.10 or newer. No legal training: the gates in the repository are the specification, and reading them is the exercise.

Nothing else is assumed for the entry-level activity below: no prior programming
experience, no particular hardware, and no home internet connection.

## Six practices this repository is set up to support

These follow the published guidance on gender-equitable STEM education — connect the
work to learners' lives, let them investigate real problems, treat struggle as part of
the work, name and challenge stereotypes, make the work collaborative, and put
learners in front of diverse role models.

1. **Connect it to their lives.** any decision with a stated rule and a stated exception — a school policy, a competition entry rule, a refund policy
2. **Let them investigate.** give the group a case that passes the gates for the wrong reason and ask them to find it
3. **Make struggle normal.** Build the session so that the first attempt is *expected*
   to fail. Say out loud that debugging is the subject, not a penalty. Ask "what did
   that error tell you?" before offering the answer.
4. **Challenge the stereotype.** Name who does this work and why it is not a gendered
   skill. Praise the method ("you isolated the variable"), not the person ("you're a
   natural") — the second kind of praise teaches learners that ability is fixed.
5. **Make it social.** one pair argues the record is admissible, one argues it is not; both must cite a gate
6. **Show diverse role models.** women in computational law and in evidence scholarship, and the engineers who build audit tooling for courts

## A 90-minute session

1. *(15 min)* Read three gates and restate each in one sentence.
2. *(25 min)* Run a sample record and check the verdict by hand.
3. *(35 min)* Write a new gate for a case the system currently gets wrong.
4. *(15 min)* Debate one borderline case, citing gates only.

## Vocabulary to define before the session

Specialist vocabulary is a hidden entry test if nobody explains it. Define each of
these the first time it appears, in one sentence, in the learners' own words:

1. **proffer** — the record of what the evidence would say.
2. **gate** — a condition that must hold before admission.
3. **inference** — a conclusion the system drew, not a fact stated.

## Accessibility

Read [ACCESSIBILITY.md](ACCESSIBILITY.md) before running a session. Two rules matter
most in a mixed-ability room:

- Every activity must be completable with a keyboard alone, with a visible focus ring.
- Every instruction names the control or the heading ("the **Run** button in the
  toolbar"), never a colour or a position.

Pair learners rather than singling anyone out, and always offer a text-only route for
a visual step.

## Contributing as a learner

Small, well-scoped contributions are the point, not a consolation prize:

- Browse issues labelled
  [`good first issue`](https://github.com/myzticalbabe/esquire-admissibility/labels/good%20first%20issue).
- Read [CONTRIBUTING.md](CONTRIBUTING.md) — it has a section written for first-time
  contributors.
- Ask in [SUPPORT.md](SUPPORT.md) if anything is unclear. Asking is expected here; it
  is not a failure.

## Licence and classroom reuse

Classroom, club and workshop use is welcome. See `LICENSE` for the exact terms, and
check whether your institution requires a separate agreement before redistributing
modified copies.
