# build-and-publish-docker-image
re-usable GitHub Actions workflow for building images
---

Description

Add a blocking quality gates to the PR validation pipeline for all in-scope repositories. A PR that fails either gate cannot be completed. Gates run automatically on PR creation and on every subsequent push; no manual trigger required.

Static code scan — no new medium+ vulnerabilities

Run SAST on every PR

Compare findings against the target branch baseline; the gate evaluates only findings introduced by the PR

If any new finding is rated Medium, High, or Critical, fail the check and block merge

Pre-existing findings on the target branch do not block, but are reported for visibility

Post a summary of new findings (rule, severity, file/line) to the PR

Document an exception path: how a false positive is suppressed, who approves, and where the suppression is recorded

Implementation requirements

Enforce via branch policy (required status check) on main and release branches, not via convention

Apply consistently across all in-scope repositories; same thresholds, same tooling

Gate results visible in the PR within the existing build validation window; target no more than [X] minutes added to PR validation

Bypass requires explicit branch policy override by a designated approver and is logged


--Acceptance criteria


A PR introducing a Medium-or-higher SAST finding cannot be completed; one with only Low findings or pre-existing findings passes

Coverage percentage and SAST summary are visible directly in the PR

Gates are enforced by branch policy on all in-scope repos

Exception/suppression process is documented and requires approval
