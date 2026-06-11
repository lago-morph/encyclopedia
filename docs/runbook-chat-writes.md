# Runbook: writing to this repo from Claude chat

Path: Claude chat -> Jentic MCP -> GitHub REST (Git Data API).

Sequence per push: `get-ref heads/main` (base commit) -> `create-tree`
(base_tree + entries with inline content) -> `create-commit` (parent = base)
-> `update-ref`. Content is authored and validated in the chat sandbox first
(YAML parse, ref resolution, kind/edge legality), and verified after by a
fresh clone from GitHub re-running the same checks.

Token: fine-grained PAT held as a Jentic credential. The target repo must be
listed under the token's Repository access AND Contents must be read/write
("code" in GitHub's summary view). Editing a token's grants does not change
its value, so Jentic needs no update.

Gotcha (les-0001): reads against a PUBLIC repo succeed with any authenticated
token and prove nothing about write access. Verify writes by writing.
