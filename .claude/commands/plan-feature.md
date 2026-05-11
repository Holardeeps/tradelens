---
description: Produce a reviewable plan before writing code for a new feature.
---

Before writing any implementation code for the requested feature, produce a
short plan I can review. Cover:

1. **Scope.** What's in, what's deliberately out, what's deferred.
2. **Affected surfaces.** Routes, components, lib modules, store, tests.
3. **Data flow.** Where data is fetched (server vs client), where state lives
   (URL, server, Zustand, TanStack Query), and why.
4. **Architecture impact.** Anything that would conflict with the rules in
   `CLAUDE.md` — call it out and propose a path.
5. **Slices.** Break the work into reviewable commits, each independently
   shippable. Match the granularity already visible in `git log`.
6. **Validation.** What confirms each slice is done — tests, manual flows,
   a11y checks, perf checks.

Do not start implementing until I confirm the plan. If anything in the brief is
ambiguous, ask before assuming.
