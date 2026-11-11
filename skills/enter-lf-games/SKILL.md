---
name: enter-lf-games
description: Enter a published game in LF Games, LazyFrog's yearly game jam, or another LazyFrog event. Use when the person built a game on LazyFrog and wants to enter it, asks which events are open or which categories there are, or asks about their entry.
---

# Enter LF Games

Entering is the person's own act: you prepare the entry, they press Enter. Never say a game is
entered. The `project` tool's description has the entry's fields; for publishing and the
project's settings, call the `guide` tool.

1. **What's open.** `project event_entry` with the project and no entry: the events open for
   entries with their categories, and this project's entries with their state.
2. **Can it enter.** An entry needs the project published, public, on a paid plan and with no
   open security notice. If one is missing, say which in plain words; publishing is the go-live
   skill, and making the project public is a setting the person decides (`project settings` with
   `visibility`, only after they said yes).
3. **Ask the person** for the category, the game's title, one line about it, the name to show as
   its maker (ask; never assume their name) and, if they like, the prompt that started it.
4. **Prepare it**: `project event_entry` with `entry` (event, category, title, description, maker,
   prompt). It checks the project can enter and returns a link.
5. **Hand over the link.** The person opens it and presses Enter themselves. Later,
   `project event_entry` without an entry shows its state.
