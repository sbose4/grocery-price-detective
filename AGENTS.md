<!-- BEGIN:nextjs-agent-rules -->

# This is NOT the Next.js you know

This version has breaking changes — APIs, conventions, and file structure may all differ from your training data. Read the relevant guide in `node_modules/next/dist/docs/` (resolved from this file's directory; in monorepos the `next` package may not be visible from the repo root) before writing any code. Heed deprecation notices.

This block is written and re-added by `next dev` — verify at `node_modules/next/dist/server/lib/generate-agent-files.js`. Removing it from a diff only re-creates the uncommitted change; committing it with your work keeps the tree clean.

<!-- END:nextjs-agent-rules -->

# Grocery Price Detective working agreement

## Development and learning workflow

- The developer has a CS degree and approximately two hours per day. Assign one cohesive, feature-based checkpoint at a time, normally one to three focused sessions. Do not split routine implementation, Git actions, and comprehension questions into separate mandatory checkpoints.
- Codex assigns checkpoints, maintains architectural consistency, handles authorized repetitive work, and independently verifies completed work. ChatGPT is the developer's primary resource for explanations, debugging, and intermediate review.
- Each assignment includes objective, relevant files and technologies, new concepts, requirements, acceptance criteria, and testing steps. Keep it concise and independently actionable.
- The developer owns approximately 60–70% of meaningful application logic and engineering decisions, especially unfamiliar concepts, backend/API work, queries, relationships, validation, business logic, React state, and integrations. This is not a line-count target.
- Do not implement the important parts of an assigned learning task or provide its complete solution unless requested. Let the developer finish several related components/functions before final verification.
- For requested help, progress from conceptual hints to implementation hints to small examples; provide a complete solution only when requested or when the developer explicitly chooses to move forward that way.
- Implement familiar, demonstrated patterns and repetitive scaffolding when it meaningfully saves time. Do not infer mastery from an explanation or a passing test alone. Check the learning record below before deciding what can be automated.
- Do not automatically rewrite submitted checkpoint code. Report substantive failures for the developer to fix. Trivial, familiar fixes may be handled only within the user's authorized scope; never silently replace learning work.
- Avoid mandatory quizzes, cosmetic blockers, unnecessary refactoring, repeated review of unchanged code, and unsolicited full-project reviews.
- Keep essential MVP work distinct from optional enhancements. Favor working end-to-end features over disconnected abstractions.

## Current and planned architecture

- Current application: a single Next.js App Router app with React, strict TypeScript, Tailwind CSS, and ESLint. Routes live in the root app directory. PostgreSQL, Prisma, authentication, storage, OCR, AI parsing, and test runners are not installed yet.
- Keep a single full-stack Next.js application. Introduce PostgreSQL and Prisma for persistence when the database checkpoint begins; no separate backend service is currently justified.
- The developer should implement meaningful REST endpoints and request handling using App Router Route Handlers in appropriate backend checkpoints. Decide concrete boundaries when that feature is assigned; do not add duplicate HTTP and Server Action interfaces for the same operation without a need.
- Use Server Components by default. Put state and event handlers behind focused Client Component boundaries. Database clients, secrets, and privileged integrations stay on the server. Read the installed Next.js documentation required by the generated block above.
- Colocate feature-specific components, fixtures, and types with their route while they remain local. Extract shared modules when real reuse appears. Avoid speculative service layers, repositories, state libraries, or design systems.
- Agreed tools for later stages: PostgreSQL, Prisma, private AWS S3 receipt storage, OCR, OpenAI-assisted parsing, Recharts, Vitest, Playwright, GitHub Actions, and Vercel. Use Docker for concrete needs such as local PostgreSQL. Do not add or replace infrastructure without explaining the need.
- Implement a useful manual receipt workflow and trustworthy price calculations before extraction and AI. Introduce authentication and ownership checks before exposing private persisted receipt data, not as final polish.

## Data correctness and security

- Initial scope uses USD. Store ordinary money amounts in integer cents; sum cents before display conversion. Later fractional quantities and unit-price calculations require an explicit precision and rounding policy and tested unit conversions.
- A receipt purchase line is a historical observation. Preserve its purchased quantity, package size/unit, and paid price; changing a product's current information must not rewrite history.
- Unknown package size is not zero. Compare compatible unit dimensions only. Keep product identity separate from package-size observations so potential shrinkflation remains detectable.
- Treat OCR and AI output as untrusted draft data. Validate its structure, preserve uncertainty, and require user correction/confirmation before using it as confirmed purchase history. Structured output does not prove factual accuracy.
- Validate external inputs at the server boundary and enforce relational integrity in the database. Apply ownership checks to every user-specific read/write, not just UI visibility.
- Keep receipts private in S3; keep credentials out of client bundles, logs, source control, and fixtures. Future uploads must validate permitted file properties and handle authorization.
- Use deeper verification for authentication, authorization, database transactions, receipt extraction, product matching, unit conversion, price calculations, and shrinkflation claims. Never trade critical correctness or security for schedule.

## Code and Git conventions

- Prefer readable functions and explicit domain types. Avoid any, unjustified casts, suppressed checks, and abstractions without current benefit.
- Use stable data IDs as React list keys. Keep state minimal and derive filtered collections and summaries from source data and user selections.
- Use semantic HTML, associated input labels, keyboard access, visible focus, and readable layouts. Cosmetic preferences alone must not block a checkpoint.
- The current default branch is master. Use descriptive feature branches, cohesive commits, and pull requests. Suggest logical commit points without requiring a return to Codex for every Git operation.
- Never commit, push, merge, publish, or send external messages on the developer's behalf without applicable authorization. Preserve unrelated working changes.
- Follow existing project conventions and explain consequential architectural changes. Preserve the generated Next.js instruction block in this file.

## Final verification contract

- Verify the actual changed source and its integration independently. A developer or ChatGPT review is useful context, not evidence that acceptance criteria pass.
- Run relevant TypeScript checks, lint, build, and configured automated tests. Current scripts are npm run lint and npm run build; the installed TypeScript compiler supports npx tsc --noEmit. Vitest and Playwright are planned, not yet configured.
- Use browser checks for interactive acceptance criteria. Report checks not run, environment failures, missing coverage, and actual results accurately. Do not describe a manual scenario as an automated test.
- Introduce meaningful automated tests with business logic and persistent workflows, and automate routine test setup when authorized. Do not write tests that merely mirror trivial implementation details.
- After a failed check, rerun affected checks after corrections; broaden verification only when changes or unresolved risks justify it.
- A checkpoint passes only when acceptance criteria are satisfied and no known critical issue remains. Optional improvements must be separate from required fixes.
- Report completed checkpoint verification using these labels:
  - Status: PASS / NEEDS CHANGES / BLOCKED
  - Acceptance Criteria: concise passed/failed requirements.
  - Verification: executed checks, results, and anything unverified.
  - Required Fixes: only blockers, with file locations and actionable descriptions.
  - Next Checkpoint: assign the next substantial feature only after PASS.
- Update the learning record below after verification: completed functionality, evidence observed, concepts newly demonstrated, unresolved learning gaps, and patterns Codex may automate. Passing tests establishes behavior, not independent mastery.

## Learning and checkpoint record

Updated: 2026-10-12. Keep this record lightweight and based on observed evidence.

| Concept | Evidence and assessment | Codex delegation |
| --- | --- | --- |
| File-based routes | Implemented /receipts and explained why the folder, not the function name, sets the URL. Basic use demonstrated. | May scaffold familiar static routes. |
| Shared layouts and Link | Correctly placed shared navigation before children, explained href versus visible text, and corrected empty links. Basic use demonstrated. | May implement repeated simple navigation and markup. |
| JSX and semantic HTML | Implemented headings, empty state, header/nav, and link children. Basic markup demonstrated; dynamic rendering is unproven. | May handle repetitive static UI. |
| Git and PR workflow | Created branches, commits, pushes, PRs, and merges with guidance. Practiced; independent conflict resolution not demonstrated. | Give consolidated Git guidance; avoid repeated drills. |
| Tailwind layout | Uses starter classes; independent layout design not yet verified. Partially understood / insufficient evidence. | May assist with routine styling; do not claim mastery. |
| TypeScript types and typed props | Earlier sample-object exercise assigned but no implementation submitted. New. | Developer implements current checkpoint. |
| Lists, keys, state, controlled inputs, derived data | No implementation submitted. New. | Developer implements current checkpoint. |
| Server/Client boundary | No implementation submitted. New. | Developer implements current checkpoint. |
| Database, REST APIs, validation, auth, business calculations, testing, integrations | Not implemented. New. | Developer owns meaningful first implementations; Codex may scaffold routine setup. |

Completed foundation: starter app and GitHub repository; homepage; receipts empty state; shared Home/Receipts navigation; feature branch and PR workflow. Homepage link click, keyboard activation, and browser Back were previously checked. Shared navigation source was reviewed and its merge reported by the developer; a separate final browser/build verification was not recorded. Do not retrospectively mark it fully tested.

### Active checkpoint: browse and filter sample receipts

- Status: ASSIGNED, not verified. Replaces the earlier single-object exercise. Estimated 2–3 two-hour sessions. Suggested branch: feat/receipt-browser.
- Objective: build an interactive /receipts browser with clearly labeled sample data, reusable typed receipt cards, a labeled store selector, and accurate displayed count/total. It will later receive persisted receipt summaries.
- Relevant files: app/receipts/page.tsx plus new sample-receipts.ts, receipt-browser.tsx, and receipt-card.tsx in the same folder. The fixtures module can export ReceiptSummary and supported store options. Keep the page a Server Component; pass fixtures to the interactive Client Component through typed props.
- ReceiptSummary fields: id and storeName strings, purchasedOn as a literal YYYY-MM-DD string, totalCents as a nonnegative integer number. IDs must be unique; use them as React keys. Display dates unchanged for this checkpoint.
- Fixtures: four receipts, Aldi at 4237 and 1805 cents; Costco at 6720 and 900 cents. Include Kroger as a supported dropdown option with no receipts so the empty state is reachable. This store list is a demo fixture, not a database design.
- Requirements: initially show All stores; display store/date/USD amount per receipt; keep only store selection as state; derive matching receipts, count, and total from props and selection; sum cents before display formatting; use two decimal places; show an empty message, zero count, and $0.00 for zero matches and an empty input array; recover correctly when switching back; preserve shared navigation and readable narrow/desktop layouts.
- Expected results: All stores = 4 / $136.62; Aldi = 2 / $60.42; Costco = 2 / $76.20; Kroger = 0 / $0.00; empty input = 0 / $0.00.
- Verification: repeated switching and actual card contents; temporary empty input restored before submission; keyboard selection and visible focus; shared navigation both ways; narrow and desktop layout checks; npm run lint, npx tsc --noEmit, npm run build; no new runtime/key errors. If generated route types are absent, generate them with installed Next tooling and rerun the type check.
- No automated test runner is configured yet. This UI checkpoint uses browser and static/build checks; do not claim automated feature coverage. Introduce meaningful automated tests with upcoming calculation/validation and persistent workflows.
- Ownership: developer implements meaningful types/props, list/card rendering, selection state, filter, total, and empty handling; ChatGPT assists learning and intermediate review; Codex independently verifies the finished checkpoint.
- Deferred: entry/editing, persistence/API, authentication, line items, price comparisons, uploads/OCR/AI, search/sort, URL-persisted filters, and complex date formatting.
- Suggested commits: typed receipt display; interactive filtering with summaries and empty handling. No intermediate Codex check-in is required.
