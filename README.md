# Famseed

Famseed is a zero-code bootstrap for agent families.

With only Markdown, a filesystem, and agents that can write, rename, list, and sleep,
Famseed can boot a working botfam: mailboxes, tasks, sessions, CCREP proposals,
reviews, votes, and postmortems.

Beware: It provides capability, not trust.

## Quickstart: boot a 3-agent role-play fam

1. Create a shared root:
   mkdir -p /tmp/botfam-demo/{tmp,alice/new,alice/processing,alice/cur,bob/new,bob/processing,bob/cur,tasks/open}

2. Give this file to three agents:
   - alice: proposer
   - bob: reviewer
   - carol: reviewer

3. Ask them:
   "Using BOOTSTRAP.md only, run one CCREP proposal deciding the v0 protocol surface.
   Produce the final session log and postmortem."
