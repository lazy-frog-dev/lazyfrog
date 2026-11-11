---
name: deploy-from-here
description: Work on a LazyFrog project from a checkout of its code and update its preview with git push, then publish. Use when the person has the code on their machine or in a cloud coding session, asks to clone a LazyFrog project, to "push to LazyFrog" or "deploy from here", or when the repository has a LazyFrog remote or a .mcp.json that points at LazyFrog.
---

# Deploy from here

The preview is the source of truth: it is what runs, what other people's AIs work on and what a
publish takes. Work in the checkout, push to update the preview, use the LazyFrog tools to look
and to publish. For detail, call the `guide` tool and read "Working from a checkout".

1. **Get the code and the remote.** A project clones from its LazyFrog address; git asks for a
   user name (anything) and a password, a personal token the person makes in their LazyFrog
   account under Access tokens ("Read and write" to push). You can't make one for them.

   ```
   git clone https://git.lazyfrog.dev/<project>.git
   ```

   In a checkout of the project's GitHub repository, add the remote once:

   ```
   git remote add lazyfrog https://git.lazyfrog.dev/<project>.git
   ```

2. **Change and try it locally** as in any repository (`compose.yml` runs the app with a database
   of its own). Commit. Never commit secrets, `.env` files, dependencies or build output: ask the
   owner for a secret with `secrets request` instead.
3. **Push to update the preview.**

   ```
   git push lazyfrog main
   ```

   Read the `remote: LazyFrog:` lines: the preview address, the build time and the migrations
   applied to the preview's database, or the step that failed with its last lines and what to do.
   Don't push again unchanged.
4. **When the push is refused**, its last line says why and nothing changed: the preview has
   commits you don't have (pull, resolve, push again; never force), a secret in a commit (take it
   out of the commits, ask for it as a secret), or another AI is working there (wait a minute).
5. **Look through the tools**: `service_status`, `logs_tail`, `http_get`, `preview_screenshot`,
   and `db_schema` and `db_read` for the preview's database, which isn't reachable from the
   machine.
6. **Publish when the person says so**: `deploy preflight`, then `deploy publish` with a one-line
   summary, followed with `job_read get` (the go-live skill has the checklist). A push publishes
   by itself only when the person turned auto-publish on.
