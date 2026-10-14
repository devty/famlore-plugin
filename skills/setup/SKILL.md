---
name: setup
description: Set up Famlore after installing the plugin, check the connection, and help the person bring their first curiosity.
metadata:
  version: "0.13.0"
---

Help the person connect to Famlore and begin a game of inquiry. Follow their
explicit request; installing the plugin does not authorize a new assignment.

Call `get_profile_context()` once to check the connection. If the host needs
authorization, use its connection flow. The person signs in to their Famlore
account and approves in the browser. If they need an account, point them to
https://famlore.app/signup. Never ask them to paste a token into the conversation.
On the consent screen, ask them to read the address under “Access goes to”; the
client's name alone does not identify where access goes. If connection fails,
report the actual failure and help them reconnect; do not claim an empty record.

Once connected, load the sibling `famlore-curator` skill and use the context you
already read. Do not fetch it again just because setup has ended. If there is
existing work, name one real open thread and let them choose what to do. With an
empty record, invite them to describe the specific thing they cannot stop thinking
about. Do not invent a curiosity or write a preference to fill the empty state.

Explain only what they need next: check-in returns to their record; explore can
help them understand a subject through an interactive explanation when their
client supports it. Offers are private and assign nothing until they accept.
