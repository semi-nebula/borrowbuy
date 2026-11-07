# Working together: GitHub and Arena

## One-time setup for each teammate

1. Create or sign in to your own GitHub account. The repository owner invites each teammate as a collaborator via the repository's GitHub settings; each person accepts the invitation. If it belongs to an organization, follow its access policy instead. Never share a login or personal access token.
2. Each person signs in to Arena on their own computer and connects their **own** GitHub account using Arena's GitHub connection flow. Authorize access to `semi-nebula/borrowbuy` when prompted. The exact screens and available permissions can change; if the repository does not appear, check the connected GitHub account, accepted invitation, and repository access granted to Arena.
3. In Arena, open a coding session for this repository and confirm the branch and base commit shown in the session. Arena sessions may be tied to their own branch: obey the branch shown in that session, rather than assuming that all sessions share one branch. You do not need a local clone to ask Arena to edit the repository.
4. Optionally, install Git and clone the repository locally from its GitHub page. Use `git clone <repository-URL>` and `cd borrowbuy`; use your own GitHub authentication. Do not paste passwords, tokens, or `.env` contents into chat or commits.

## Routine for each task

1. Read [the shared Arena handoff](arena-handoff.md). Swastik and Swayam can each take frontend or backend work under the backup plan. Agree on a small task and who owns it; avoid two people editing the same files at the same time when possible. Start a fresh session from the latest integrated `main` when the Arena interface allows it. Existing sessions can be based on older commits: check the branch and history and use the session's supported update workflow before starting.
2. Ask Arena to read `README.md`, `docs/` and relevant code first, explain the task, and run relevant tests. Example: “Read the project docs and current code. Implement the listing API according to the agreed contract, add tests, and update the README with accurate status. Do not commit secrets.”
3. Review the diff and tests; manually check the feature too. Ask for changes if needed. Have Arena commit on **its assigned session branch** and open a pull request into `main`, or use GitHub's interface. A saved Arena edit is not automatically a commit or visible to other sessions. Push the branch before opening a PR if required.
4. Another teammate reviews the PR, resolves conflicts carefully, and merges it after checks pass. Tell other teammates when `main` changes. Their sessions must incorporate the new commit or start fresh before building on it; a README alone does not sync code or chat memory.
5. Update the README status, actual run/test commands and relevant docs in the same PR as the change. Do not mark planned work complete. Keep small PRs and meaningful commit messages so others can follow the history.

For local Git work, use a separate branch per task, fetch the latest changes and integrate them according to your team's Git workflow. Do not force-push over someone else's work. Arena's fixed-branch instructions take precedence inside an Arena session.

## If access fails

- Confirm the invitation was accepted, the correct GitHub account is connected, and the repo is included in the GitHub app's access.
- Check whether organization restrictions or repository permissions require owner approval.
- If authentication fails in Arena, reconnect GitHub in Arena; never send credentials in chat.
- If a PR conflicts, coordinate with its owner and resolve against the latest base; re-run tests before merging.
