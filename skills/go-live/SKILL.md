---
name: go-live
description: Publish a LazyFrog project to its live address and connect the person's own domain. Use when the person says "publish", "go live", "launch", "put it online for everyone", "use my domain", or asks what is left before launch.
---

# Go live

Publishing is outward-facing: it waits for the person's yes. For detail, call the `guide` tool and
read "Publishing" and "Custom domains".

**Plan.** Publishing needs a paid LazyFrog plan (Hobby or higher); Free builds and previews only.
On Free the publish is refused with a plan-limit answer: say once, plainly, that going live needs a
paid plan and that the preview stays free to share; the person changes plan themselves in their
LazyFrog account. Never start or promise a payment. Then carry on in the preview.

## Publish

1. **Preflight first**: `deploy preflight`, followed with `job_read get`. It checks secrets, the
   services, the build, the pending migrations on a copy of the live database and the health check.
2. **Fix what it found.** Keys or passwords written in the code: ask the person once for the whole
   batch before moving them to secrets. A destructive migration needs their explicit yes.
3. **First publish**: the live site starts with an empty database unless the preflight offers to
   copy the preview's data once; ask before accepting that offer.
4. **Publish when they say so**: `deploy publish` with a one- or two-sentence summary from the
   commits, followed with `job_read get`. Then check the live site with `http_get` (`env`
   production) and give the person the live address.
5. **If it goes wrong**, the old version stays live. `deploy rollback` brings back an earlier
   publish in seconds; restoring the live database needs the person's approval.

## Their own domain (paid plans)

1. `domain_read check` the name they want, and a few alternatives. LazyFrog doesn't sell domains:
   they buy theirs wherever they like; never quote a price.
2. `domain add` connects it to the project, then give the DNS records exactly as returned, and
   tell them to keep their existing mail records.
3. `domain_read status` or `domain verify` later, and `domain_list` for the state of all of them.
