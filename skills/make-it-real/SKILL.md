---
name: make-it-real
description: Turn a prototype made in this conversation into a real, hosted app on LazyFrog. Use when the person likes something built in the chat (an artifact, a page previewed from a code block, a single component) and wants it online for real, with its own address, data that is kept, sign-in for visitors or their own domain; or says "make this real", "put this online", "host this", "turn this into an app".
---

# Make it real

The prototype has no repository: you send its files and LazyFrog lays them out as a project. The
prototype stays as it is where it was made. For detail, call the `guide` tool and read "Make it
real: from a chat prototype to a project".

1. **Read the guide** with `guide` once in this conversation, if you haven't.
2. **Collect the source as it is.** You have it in this conversation; otherwise ask the person to
   paste it. Don't change it before the import: the import reads it as it is.
3. **Import it** with `project import` and `source.files`: each file's `path` as the prototype has
   it (`index.html`, `App.tsx`, `styles.css`) and its `content` as text; an image or a font with
   `encoding` set to base64. Up to 100 files and 3 MB together; for more, import the page and what
   it needs, then send the rest with `fs_write`. It returns a job: follow it with `job_read get`.
4. **Look before changing anything.** `preview_screenshot` of the new preview: it should look like
   the prototype. Give the person the preview address.
5. **Plan from the checklist.** The job's result carries a checklist (also in `project_read
   about`): what moved, what must change (each call with its file and lines), what LazyFrog adds.
   Save the plan (`plan save`), show it, ask only what the prototype can't answer in one round,
   and wait for their reply: only the person approves a plan. Record their yes with `plan agree`
   and `said` (their own words) in a later turn; if they said just build it, `plan agree` with
   `defaults` set to true instead.
6. **Work through what must change**, one item at a time, checking each with a screenshot:
   - data kept in the browser or the chat app's storage moves to the project's database: a
     migration with a table for each kind of thing, and the app's own routes reading and writing it;
   - calls to the chat app's AI become a route of the app that uses the owner's own provider key
     (the owner pays for those calls now, not each visitor: say so plainly);
   - data read from the person's connected apps: they connect the source to the app itself, or
     export the data for you to import;
   - packages loaded from a CDN address are imported by name.
7. **Say what they gained** in a line: a public address anyone can open, kept data, forms, sign-in
   for visitors, a preview to try changes on, snapshots and an export whenever they want one.
8. **Publishing is a separate step** that waits for the person's yes (the go-live skill).

Never call the prototype "live" before it is published: until then it is a preview.
