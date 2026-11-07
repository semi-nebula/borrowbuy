# Build plan and working agreement

## Goal and scope

Help verified students discover and borrow useful campus items safely. A narrow MVP is more achievable than the full synopsis. Proposed phases below are **not implemented**. Agree on these decisions together before coding and update this document when the contract changes.

## Part 1 — Design together

- Write user stories and sketch mobile-friendly screens: sign-in, browse/search, listing detail, create listing, incoming/outgoing requests and profile.
- Agree on a simple data model: User (verified college identity), Listing (owner, title, description, category, price/deposit terms, availability), BorrowRequest (listing, borrower, status and dates), and eventually Review/condition evidence.
- Decide whether the MVP has free borrowing only or charges/deposits. Display agreed terms clearly; do not implement real payments until the team has an explicit design and safeguards.
- Decide how campus identities will be verified. A verified `@vit.edu` email is the proposed first step; domain ownership alone does not prove student status or prevent multiple institutional accounts per student. A true one-account-per-college-ID rule needs an authoritative, privacy-conscious verification mechanism and college approval. Do not promise it before that exists.

## Part 2 — Foundation

- Backend: scaffold Node/Express, configuration, database connection and health endpoint; add automated tests, input validation and a `.env.example` with placeholders only.
- Frontend: scaffold React/Vite, routing and reusable accessible components; make responsive mock screens using sample data, visibly marked as mock.
- Both: agree on Node version, scripts, environment variables, and formatting; add setup and test instructions. Use relative `/api` URLs from the browser and a dev proxy to the API, not browser-side localhost URLs, so previews can work.

## Part 3 — Authentication and listings

- Backend: implement an agreed server-verified identity provider or email verification, restrict access to verified allowed-domain users, and enforce owner-only edits. Implement create, browse, detail and edit for listings. Validate all input server-side and prevent clients from selecting another owner.
- Frontend: build login, browse/search, listing details and create/edit forms; handle loading, empty, error and unauthorized states. Use mock data only until the API is ready.
- Joint: connect frontend to API, test two accounts and unauthorized actions. Keep listings and user data minimal; never expose sensitive identifiers publicly.

## Part 4 — Borrow and return

- Backend: implement request creation and a state machine: `pending` → `accepted` or `declined`; accepted → `returned`. Only the owner accepts/declines; define and test who records return. Prevent self-requests and conflicting accepted bookings using server-side checks. Keep agreed price/deposit terms in a server-stored request snapshot so later listing edits do not silently change existing agreements.
- Frontend: request form, owner inbox, status display and return flow. Explain the agreed dates and terms before confirmation.
- Joint: walk through two users, including forbidden actions and competing requests; record real screenshots for the review.

## Part 5 — Trust and later work

Reviews only after a completed transaction, late-return handling, disputes, condition photos, notifications, QR handovers and trust scores are planned extensions, not MVP claims. Before building them, decide fair rules with the guide: who can review, when a delay or damage fee applies, dispute/appeal process and who can suspend an account. A one-day delay should not automatically trigger a severe penalty; no unilateral automatic fee. Photos require consent, secure access, retention/deletion rules and server-recorded timestamps; a “live photo” cannot by itself prove authenticity. Show only proportionate, accurate profile information. Do not claim that any design eliminates fraud or hacking.

## Proposed API contract (agree before implementation)

All paths are under `/api`; JSON responses and a consistent error format should be defined during implementation. IDs are opaque server-generated values. Authentication travels via the chosen secure mechanism; do not put tokens in URLs. These are proposed endpoints, not working routes:

| Method and path | Purpose | Authorization |
| --- | --- | --- |
| `GET /health` | Service health | Public, no sensitive details |
| `GET /listings` and `GET /listings/:id` | Search and view | Verified user |
| `POST /listings` | Create listing | Verified user; server sets owner |
| `PATCH /listings/:id` | Edit listing | Owner only |
| `POST /listings/:id/requests` | Request dates | Verified user, not owner |
| `GET /requests` | Own incoming/outgoing requests | Parties only |
| `POST /requests/:id/accept`, `/decline`, `/return` | Transition request | Owner for accept/decline; return policy TBD |

Before coding, agree precise request/response fields, date/time zone, pagination, status codes, validation errors, concurrent-booking behavior and the return confirmation policy. Version changes together; frontend can use matching mock responses.

## Security baseline

Use HTTPS in deployment; verify identity and authorization on every protected API request, validate and limit inputs/uploads, use secure session handling, rate-limit sensitive actions, keep dependencies updated, and log security events without secrets or unnecessary personal information. Store credentials in environment variables or a secret manager, never in Git. Back up data and test access controls. Restrict CORS to known origins in production. These reduce risk but do not guarantee security. No real student data or real payments in an unprotected prototype.

## Definition of done for each part

A reviewer can run documented setup and tests, verify the user flow and failure cases, inspect the PR, and see an accurate README status. Each teammate can explain their own work. Record unfinished decisions and limitations rather than presenting them as completed.
