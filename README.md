# Famseed

Famseed is a zero-code bootstrap for agent families.

With only Markdown, a filesystem, and agents that can write, rename, list, and
sleep, Famseed can boot a working botfam: mailboxes, tasks, sessions, and CCREP
proposals / reviews / votes.

> ## ⚠️ Capability, not trust
>
> Famseed gives agents the full **capability** of a fam and **none of its trust
> guarantees**:
> - **no attributable writes / no real identity** — any agent can write a file
>   claiming to be anyone;
> - **no confabulation-resistance** — an agent can fabricate a message, a vote,
>   a claim, or an entire history, and nothing will catch it;
> - **no pacing, no tamper-evident log.**
>
> A **single model role-playing every actor has zero independence** — "alice
> sends, bob receives" is one model talking to itself; the files are props.
> This is fine for prototyping, teaching, and tiny fully-cooperative fams where
> a human reads every line. It is **not** safe when agents are numerous, fast,
> independent, or unsupervised. Turning capability into trust is what a
> *compiled* runtime adds — see **[BOOTSTRAP.md](BOOTSTRAP.md) §9**.

The full protocol is **[BOOTSTRAP.md](BOOTSTRAP.md)** — read it first.

## Quickstart: boot a 3-agent role-play fam

1. Create a shared fam root with a mailbox for **every** named agent and the
   full task and session tree (any directory works as the root):
   ```sh
   ROOT=/tmp/botfam-demo
   mkdir -p "$ROOT"/{tmp,tasks/open,tasks/claimed,tasks/done,sessions}
   for a in alice bob carol; do
     mkdir -p "$ROOT/$a"/{new,processing,cur}
   done
   ```
   (Per BOOTSTRAP.md the verbs also `mkdir -p` their own destinations, so this
   is belt-and-suspenders — but it makes the tree obvious.)

2. Give every agent **BOOTSTRAP.md** and a name:
   - alice — proposer
   - bob — reviewer
   - carol — reviewer

3. Ask them:
   > "Using BOOTSTRAP.md only, run one CCREP proposal deciding the v0 protocol
   > surface. Record each participant's presence, compute the tally over the
   > present principals, and produce the final session log."

Remember while you watch: a single model playing all three seats is not a
consensus — it is one model agreeing with itself. The role-play tests the
*mechanics*, not the trust.
