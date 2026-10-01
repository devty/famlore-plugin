# Famlore

The assignment comes through. Where you solve it is up to you.

Famlore is a game of inquiry. Whoever you already talk to keeps the record of
the subject you are furthest into and hands you one specific thing to go find
out — ask them, point a tool at it, read the actual thing, go outside and look.
It notices the threads between your rabbit holes, sets the occasional field
assignment, and keeps a record of how you think. It is deliberately restrained:
it looks every session, and acts only when there is something real to offer.

## Rooms

Rooms are topical spaces where other people deep in the same thing can find each
other. Everything else here is private and solo; rooms are the one place you
become visible to anyone.

That only happens if you say so. Joining is an explicit act, and it shows the
room exactly two things you wrote: your handle and a one-line blurb about what
draws you to the topic — plus when you joined. It never shows your rabbit holes,
your field assignments, or anything you submitted for one. You can leave any
time, which removes your entry from that room immediately.

## Install

This plugin is the Claude Code route. **In Claude Desktop or claude.ai there is
no plugin to install** — add `https://famlore.app/mcp` as a custom connector
instead. Same browser approval, same absence of a key, same tools. The server
gives every client a short brief on how the Curator works; what the connector
gives up is the full Curator skill below, which only a plugin can carry. Neither
route is a lesser one, and most people take the connector.

In Claude Code:

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
  how it uses the tools, including what joining a room does and does not
  expose. The thinking happens in *your* client, which is why the persona ships
  with the plugin rather than living on a server.
- **`skills/check-in/`** — `/famlore:check-in`, an invoke-only check-in for when
  you want to ask rather than wait.

## Access

Anyone can sign up at [famlore.app](https://famlore.app/signup) — no invite
code needed. Approving the connection asks you to sign in, so make the account
first.

## What it sends, and where

The plugin runs nothing on your machine. It connects your Claude client to one
place: Famlore's MCP server at `https://famlore.app/mcp`, over an OAuth
connection you approve. When the Curator calls a Famlore tool, what goes to
that server is what the tool is for: the curiosities you describe, the
assignments you accept, the evidence you submit, and your choices about rooms
and visibility. Famlore stores it in your account, and nothing else is sent
anywhere by the plugin.

Famlore records basic analytics about tool calls (which tool, how long it took,
whether it failed, and a fixed label for what it does), never the words you or
your AI wrote in the call.

## Privacy

What Famlore stores, how long it keeps it, and how to delete your account:
[famlore.app/legal/privacy](https://famlore.app/legal/privacy).

## License

Licensed under the Famlore Plugin Limited Use License. You may install and use
the plugin to connect your AI client to Famlore; it is not open source. See
[LICENSE](LICENSE).

## A note on this repository

This is a **published artifact**. It is generated from the private application
repository and pushed here by a script, so edits made directly to this repo will
be overwritten on the next publish.

