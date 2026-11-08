# BorrowBuy

A proposed campus peer-to-peer borrowing platform: students can lend underused items such as calculators, lab coats and books instead of everyone buying their own. Registered project title: **A Trust-Centric Peer-to-Peer Utility and Asset Sharing Platform for Campus Communities**.

## Current status

A **static, multi-page frontend prototype** is available in `frontend/`, inspired by the selected UI references. It uses fictional sample data and browser-only storage for demo listings, requests and chat. There is **no backend, database, real authentication, real messaging, payment, verified identity or deployment** yet. The prototype is not a PWA yet. Do not enter real credentials or sensitive data. Update this section when work is integrated; check the code and history before making claims.

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

For the prototype, allow sign-up with any email address; do not restrict accounts to a college email domain. First aim for a demonstrable flow: a signed-in user creates a listing, another user finds it and requests it, the owner accepts or declines, and the return can be recorded. Authentication and authorization must be enforced on the server, not just in the UI. Any-email sign-up does not verify campus membership or guarantee one account per person. See the build plan for boundaries, security and later features.

## Repository map

- `README.md` — current status and entry point for the team and future Arena sessions.
- `docs/arena-handoff.md` — shared context, backup plan and instructions for both Arena chats.
- `docs/collaboration.md` — GitHub access, Arena sessions and safe integration.
- `docs/build-plan.md` — phased work, proposed interface, trust and security decisions.
- `docs/mid-sem-review.md` — deliverables and evidence checklist based on the supplied notice.
- `docs/source-summary.md` — privacy-conscious summary of the supplied documents.
- `docs/source-documents/` — supplied security notes, assessment notice and review guide; see its README for the privately held registration form.
- `frontend/` — static HTML pages with embedded CSS and JavaScript, image assets, and local sample data.
- `references1/` — selected UI reference images.
- `LICENSE` — MIT license.

## Run the frontend prototype

No dependencies are required. From the repository root, run `python3 -m http.server 8000 --directory frontend` and open `http://localhost:8000/`. The static pages also work in a suitable static hosting environment. Demo data is saved in browser local storage; clearing site data resets it. This is not real authentication or communication. Never enter secrets or real student data.

Each page contains its own embedded styling and JavaScript for browser-only interactions; there is no build step. To deploy, upload the contents of `frontend/` (including `assets/`) to any static host with `index.html` as the entry page. The prototype is not a secure or multi-user application.
