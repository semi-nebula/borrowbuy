# BorrowBuy

A proposed campus peer-to-peer borrowing platform: students can lend underused items such as calculators, lab coats and books instead of everyone buying their own. Registered project title: **A Trust-Centric Peer-to-Peer Utility and Asset Sharing Platform for Campus Communities**.

## Current status

This repository currently contains the MIT license and project planning documentation. **There is no application, API, database, login or deployment yet.** The stack and features below are proposals, not completed work. Update this section whenever work is merged; check Git history and the actual code as well as this README before making claims.

## Team

| Member | Initial responsibility |
| --- | --- |
| Swastik (project owner) and Swayam | Backup plan: both work across frontend and backend |
| Suyash and Tamanna | Original plan: frontend, UI/UX and accessibility; coordinate actual participation with the group |

The original team plan assigned Swastik and Swayam to backend and Suyash and Tamanna to frontend. As a backup, Swastik and Swayam have decided to cover both frontend and backend. This does not change or invent anyone else's actual contribution. All four should coordinate research, review preparation, testing and the viva. See [the shared Arena handoff](docs/arena-handoff.md).

## Start here

1. Read [the shared Arena handoff](docs/arena-handoff.md) and [collaboration and Arena setup](docs/collaboration.md) on each computer. Make sure everyone has their **own** GitHub and Arena accounts and repository access.
2. Agree on the MVP and shared API contract in [the build plan](docs/build-plan.md). The frontend and backend can work in parallel against that contract.
3. Follow the [mid-semester checklist](docs/mid-sem-review.md) alongside development; the notice does not require a finished app.
4. Before an Arena coding session, use the latest integrated commit and ask it to read this README and the docs. Inspect its changes, test, commit, and integrate through a reviewed pull request.

## Suggested MVP and direction

A mobile-friendly **web app** is the smallest starting point. Proposed stack, subject to team agreement: React + Vite for the UI, Node.js + Express for the API, and MongoDB for persistence, consistent with the project synopsis. Agree on authentication and deployment before implementing them; no credentials or service setup are included here.

First aim for a demonstrable flow: a verified campus user creates a listing, another user finds it and requests it, the owner accepts or declines, and both can record return. Verification and authorization must be enforced on the server, not just in the UI. See the build plan for boundaries, security and later features.

## Repository map

- `README.md` — current status and entry point for the team and future Arena sessions.
- `docs/arena-handoff.md` — shared context, backup plan and instructions for both Arena chats.
- `docs/collaboration.md` — GitHub access, Arena sessions and safe integration.
- `docs/build-plan.md` — phased work, proposed interface, trust and security decisions.
- `docs/mid-sem-review.md` — deliverables and evidence checklist based on the supplied notice.
- `LICENSE` — MIT license.

There are no install, run, or test commands yet. Add accurate commands here once the app is scaffolded, and never commit secrets or real student data.
