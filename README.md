# Famlore

A memory for the one thing you can't stop thinking about — and the field
assignments that come out of it.

Famlore plugs into the assistant you already talk to and gives it somewhere to
keep your rabbit holes. It notices the threads between them, sets the occasional
field assignment, and keeps a record of how you think. It is deliberately
restrained: it looks every session, and acts only when there is something real
to offer.

## Install

```bash
claude plugin marketplace add devty/famlore-plugin
claude plugin install famlore@famlore
```

Restart Claude Code. There is no key to copy — the first tool call returns a 401
that points your client at the authorization server, it registers itself, and a
browser opens for you to approve.

**On the consent screen, read the address under "Access goes to", not the name
at the top.** Any application can call itself anything; only the redirect
address is registered and enforced.

Then `/famlore:check-in` to check in with the Curator.

## What's in here

- **`.mcp.json`** — the connection to Famlore's MCP server. Data and storage
  only; no model runs on that server.
- **`skills/famlore-curator/`** — the Curator: who it is, when it speaks, and
  how it uses the tools. The thinking happens in *your* client, which is why
  the persona ships with the plugin rather than living on a server.
- **`skills/check-in/`** — `/famlore:check-in`, an invoke-only check-in for when
  you want to ask rather than wait.

## Access

Famlore is invite-only while it is being tested.

## A note on this repository

This is a **published artifact**. It is generated from the private application
repository and pushed here by a script, so edits made directly to this repo will
be overwritten on the next publish.

