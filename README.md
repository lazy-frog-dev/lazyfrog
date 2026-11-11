# LazyFrog

Build, host and publish real web apps with the AI you already use. LazyFrog gives each app a
project of its own: the code in a private workspace, a database, files, a preview address to try
it on, a public address when you publish, and your own domain on a paid plan. You can export all
of it at any time.

This plugin adds the LazyFrog connector and six skills that teach your AI how to work with it.

## What it does

| Skill | When it helps |
|---|---|
| make-it-real | You made a prototype in the chat and want it to become a real app with its own address and kept data. |
| deploy-from-here | You work on the code in a checkout and want `git push` to update the preview. |
| check-my-site | You want to know how the site is doing: status, logs, screenshots, form entries, live data. Changes nothing. |
| go-live | You are ready to publish, or want to connect your own domain. |
| fix-it | Something is broken or looks wrong, and you want it fixed without a redesign. |
| enter-lf-games | You built a game and want to enter it in LF Games, LazyFrog's yearly game jam. |

## Install

In Claude Code:

```
/plugin marketplace add lazy-frog-dev/lazyfrog
/plugin install lazyfrog@lazyfrog
```

Or in a terminal: `claude plugin marketplace add lazy-frog-dev/lazyfrog`, then
`claude plugin install lazyfrog@lazyfrog`. For Claude, Claude Desktop, ChatGPT and Codex, connect
LazyFrog as a connector instead: [lazyfrog.dev/connect](https://lazyfrog.dev/connect).

## Use it

1. Install the plugin, then connect LazyFrog when your AI app asks (or from the plugin's
   connectors). You sign in to your LazyFrog account and choose what your AI may do; you can
   disconnect it at any time in your account under Connected AIs.
2. Ask in your own words: "Make this a real app", "Is my site up?", "Publish it", "Connect my
   domain", "The menu is broken on phones". The matching skill guides your AI through the steps,
   and LazyFrog's own guide (a tool of the connector) has the detail.
3. For something new, your AI shows you a short plan and asks what only you know, then waits:
   only you approve a plan (or say "just build it"). Things that cannot be undone, publishing and
   anything involving money wait for your yes too. Your AI never pays for anything and never
   enters an event for you.

Works with Claude, Claude Desktop, Claude Code, ChatGPT and Codex. More:
[lazyfrog.dev/docs](https://lazyfrog.dev/docs). Is LazyFrog itself up:
[lazyfrog.dev/status](https://lazyfrog.dev/status).

## Plans

Free is for building and trying: one project with a database, snapshots and a preview at its own
address that anyone with the link can open while the month's preview hours last. Free has no
live site: publishing, at `name.lazyfrog.app` or your own domain, starts with Hobby ($9 a month);
Pro ($29) and Business ($79) are for more and bigger sites (prices a month, before tax). You
choose and change your plan in your LazyFrog account, never in the chat. Details:
[lazyfrog.dev/pricing](https://lazyfrog.dev/pricing).

## What data it sends

The skills are text only: they run no code and send nothing themselves. Everything goes through
the **LazyFrog connector** at `https://mcp.lazyfrog.dev/mcp`, signed in as you: what you ask your
AI to build or check (code, files, database queries and their answers, settings) travels between
your AI app and **your LazyFrog account**, and stays in your account and your projects. LazyFrog
never sees your conversation with your AI, only the tool calls it makes, and doesn't sell or share
personal data for advertising. Secret values (keys, passwords) are never shown to your AI.
Details: [privacy policy](https://lazyfrog.dev/legal/privacy) ·
[terms](https://lazyfrog.dev/legal/terms) ·
[acceptable use](https://lazyfrog.dev/legal/acceptable-use) · support:
[support@lazyfrog.dev](mailto:support@lazyfrog.dev) or
[lazyfrog.dev/contact](https://lazyfrog.dev/contact).

## License

MIT. See [LICENSE](LICENSE).
