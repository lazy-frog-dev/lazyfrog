---
name: fix-it
description: Fix a specific problem on a LazyFrog site or app without redesigning it. Use when the person reports something broken or wrong ("the button does nothing", "the photo is missing", "it's broken on phones"), when a check found problems, or when they ask you to "polish" or "clean up" the site.
---

# Fix it

Fix what the finding names, at its source, and nothing else. For detail, call the `guide` tool and
read "Changing an existing site".

## The rules

- **Fix what is named.** A reported problem or a check's finding, fixed where it comes from: the
  file, the component, the stylesheet rule really in force. Never stack another override on top.
- **Never redesign.** Keep the page's own look; restyle only what a finding names. "Polish" is one
  bounded pass, not a new design and not new content.
- **Never remove or replace the owner's content.** A broken image or link, a missing photo or a
  wrong detail is marked in the markup with `data-lf-placeholder="what they should supply"` and
  named in your report, never deleted and never swapped for something you made up.

## The method

1. `preview_screenshot` of each page you will touch, before changing anything (if the screenshot
   service is busy, that is LazyFrog's queue, not the app: try again in a minute).
2. `design_check` on those pages; `fs_read` the code that renders the part you are fixing (don't
   guess from the screenshot).
3. Make the smallest change at the source with `fs_edit` or `fs_write`.
4. `preview_screenshot` again with `compare` set to true: it says what changed and what didn't. A
   change meant for one part that moved another shows there.
5. **Report and stop**: what you found, what you fixed (files), how much each page changed, and
   what you left alone and why (anything that needs the person's decision, every placeholder you
   marked). Another pass only when they ask for one.

The fix reaches the live site only when the person publishes (the go-live skill).
