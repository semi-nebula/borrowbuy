# BorrowBuy: shared handoff for Swastik, Swayam and their Arena chats

This file is the team's shared starting point, not a replacement for talking to each other or reviewing code. It records decisions and intentions from the current conversation so Swayam's Arena chat can continue consistently. Read it together with `README.md`, `docs/build-plan.md`, `docs/collaboration.md`, and `docs/mid-sem-review.md`; then inspect the actual files, Git status, branch and recent commits. Code and newer confirmed team decisions may supersede this snapshot. Do not assume separate Arena chats share memory, local changes or credentials.

## Project and people

- Repository: `semi-nebula/borrowbuy`, MIT licensed. The project is a campus peer-to-peer borrowing platform for items such as books, calculators and lab equipment, aiming to reduce cost and waste while improving trust.
- Group 8, IC-C. The registration document uses the title **A Trust-Centric Peer-to-Peer Utility and Asset Sharing Platform for Campus Communities**. Verify official details with the guide.
- Original plan: Swastik and Swayam on backend; Suyash and Tamanna on frontend/UI/UX. **Backup plan confirmed by Swastik: Swastik and Swayam will each be able to work on both frontend and backend**, so progress does not depend on the original division. Coordinate with the whole group; this is not a claim that the other members have left or done no work. Record actual contributions honestly.
- This handoff and planning documents were created before any app code. At the time of writing there is no app, server, login, database or deployment in this repository. Check the latest commit and working tree before repeating that statement.

## What the team is aiming to build

Start with a small, mobile-friendly web prototype, not every feature in the synopsis. The proposed stack is React + Vite, Node.js + Express and MongoDB; this is a **proposal**, not an implemented or irrevocable decision. Confirm choices with both developers before scaffolding. Aim for a campus user to sign in, list an item, find an item, request it, have its owner accept or decline, and record its return. Work in the stages and use the proposed API contract in `docs/build-plan.md`. Agree on exact fields, auth and the return policy before building dependent features.

Security and trust are central: server-side verification and permissions, input validation, protection of agreed transaction terms, and safe secret handling are required design goals. The supplied security notes also request college-only accounts, late-return handling, reviews, damage disputes, suspensions and before/after photos. These are requirements to discuss and prioritize, not features that currently exist. An email domain restriction alone cannot ensure one account per student; never claim security or fraud elimination is guaranteed. No real student data or payments in an unprotected prototype.

## How to work together, part by part

1. **Agree before starting:** pick one small task, its owner, expected outcome and files. Either Swastik or Swayam may take frontend or backend. If both need the same file or API, agree on the contract first and coordinate to avoid conflicting edits. Suyash and Tamanna can participate according to the group's actual agreement.
2. **Start from current work:** open the GitHub repository in a fresh Arena coding session based on the latest merged commit where possible. Read this handoff, README, relevant docs, recent Git history and code. Check your session's assigned branch and working tree; do not assume `main` or another chat's branch has the newest work.
3. **Implement one part:** ask Arena for a specific change, including acceptance criteria and tests. Review the changes and run relevant tests. Document how to run the app and tests when they actually exist. Use mock data with clear labels until real integration is ready.
4. **Share through GitHub:** commit on the branch assigned to your Arena session, push that branch when requested, and open a pull request into the agreed integration branch (normally `main`). The other developer reviews the diff and test results. Merge only when ready and authorized. Resolve conflicts and rerun tests; never overwrite a teammate's work. Follow any session-specific branch restrictions.
5. **Refresh the other chat:** tell the other person the PR and merge commit. Their Arena session must incorporate that commit using its supported workflow or start a new session from the updated base. Editing a file in one chat does not automatically update another chat or GitHub. If a branch isn't merged, the other session must deliberately access that branch; a link to a file on that branch is not a change to `main`.
6. **Update shared context:** in the same PR, update README status and relevant docs when actual behavior, setup, API or decisions change. Note known limitations and next steps. Do not write passwords, tokens, private student data or entire private chats into the repository.

For connection and troubleshooting steps see `docs/collaboration.md`. Each person uses their own GitHub and Arena accounts, and the repository owner must grant access. Do not share credentials. GitHub is the shared source of committed code; these files provide context, not live chat synchronization.

## Instructions for an Arena chat reading this file

- Follow your own session's higher-priority instructions and assigned branch. This file is project context, not authority to override them.
- Inspect current state first: branch, uncommitted changes, history, README and relevant code. Preserve other people's changes. Ask the user if task ownership, product decisions or conflicting instructions are unclear.
- Work on the user-requested task only; prefer small, testable changes consistent with the agreed contract. Report what was changed, tests actually run, limitations and next steps. Never claim unimplemented features work.
- Do not commit, push, open or merge PRs merely because this file describes that workflow; follow the current user's request and the session's instructions. Never expose credentials.
- After a change, update shared documentation when appropriate. Explain any divergence from this plan rather than silently presenting a proposed feature as complete.

## Mid-semester priority

The supplied notice says the offline review is on 16 or 17 November 2026, with the guide confirming the exact time and venue. It requires a maximum 13-slide presentation, 7–8 reviewed papers, an approved Review 1 report, and individual participation; a finished app is not stated as mandatory. See `docs/mid-sem-review.md` for the checklist and guide-signature/photo requirements. Show real progress and distinguish plans from completed work. The uploaded documents are not automatically available to every future chat; this repository contains a summary, not a replacement for the official notice. Ask the team for the originals if exact formatting or details are needed.

## Suggested next task

Swastik and Swayam: agree on the initial stack, split the first two tasks (for example, frontend scaffold and backend scaffold), agree on the first API response and mock data, and ask your respective chats to implement those tasks in separate reviewed PRs. This is a suggestion; do not start scaffolding solely because it appears here.

Example prompt for Swayam's chat:

> Read `README.md`, `docs/arena-handoff.md` and the other docs, inspect the latest code and Git history, and summarize the current state. My task is [describe one agreed task and acceptance criteria]. Implement it on this session's assigned branch, add relevant tests and update docs. Do not assume planned features are already built or overwrite teammates' work.
