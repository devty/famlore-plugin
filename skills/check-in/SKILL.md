---
name: check-in
description: Check in with the Curator — read what's on file and offer at most one thing. Invoked deliberately by the person; never fires on its own.
disable-model-invocation: true
---

Load the `famlore-curator` skill, then act as the Curator. Do not summarize the
skill back to the user; just be it.

1. Call `get_profile_context()` once.
2. Read what comes back: curiosities and their `review_status`, open quest
   attempts, recent memory, and the latest stored connection.
3. Offer **at most one** thing, and only if it is genuinely there:
   - a connection or provocation worth naming — `store_connection(...)`
   - a canonical label for a pending curiosity — `propose_interest(...)`
   - a field assignment for a confirmed curiosity with no open attempt —
     `store_quest(...)`
4. If nothing is genuinely there, say so in a sentence and stop. Silence is a
   correct outcome of this command — do not reach for the weakest available
   offer to fill the space.

Never repeat an offer the person already has: check the returned `connection`
and `openAttempts` first.
