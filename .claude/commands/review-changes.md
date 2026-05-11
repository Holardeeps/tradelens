---
description: Review the pending diff against project conventions before commit.
---

Review the working tree changes against `CLAUDE.md` and the project's
established conventions. Run `git diff` and `git status` first.

Check, in order:

- **Server vs client boundary.** Is every new `"use client"` justified? Could
  the component stay server?
- **Listing state location.** Did filter, sort, or pagination state leak into
  a store instead of the URL?
- **Zustand discipline.** Does the store still hold UI-only state? Any
  server-shaped data sneaking in?
- **Data access centralization.** Did any component call `fetch()` directly
  instead of extending `lib/api/products.ts`?
- **TanStack Query scope.** Is it still enhancement-only (prefetch, cache
  hydration), or did it become the primary data path?
- **States on new surfaces.** Loading, error, and empty all present?
- **Accessibility.** Landmarks, accessible names, keyboard reachable, focus
  return on dismissible surfaces?
- **Tests.** Did new parsing or logic gain coverage? (Rendering chrome doesn't
  need to.)
- **Static checks.** `npm run lint`, `npx tsc --noEmit`,
  `npm run test -- --run` — report any failures.

Report findings grouped by severity (blocker / should-fix / nit). Do not
propose fixes unless I ask for them.
