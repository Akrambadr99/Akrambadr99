<p align="center">
  <img src="assets/profile-python-typescript.svg" alt="Akram Badr — Python and TypeScript, AI code evaluation, debugging and test automation" width="100%">
</p>

<p align="center">
  <strong>AI-generated code review · Python and TypeScript · Bug fixing and regression tests</strong>
</p>

I'm Akram, a software engineer with **3 years of hands-on software project experience**. My work combines **professional Python-based AI coding evaluation** with **TypeScript application development**: reproducing bugs, reviewing proposed fixes, and checking behavior with automated tests.

<p align="center">
  <a href="#ai-code-review-and-test-engineering">AI code review</a> ·
  <a href="#selected-projects">Selected projects</a> ·
  <a href="#debugging-examples">Debugging examples</a> ·
  <a href="#toolbox">Toolbox</a>
</p>

## AI code review and test engineering

My professional Python work focuses on evaluating whether AI-generated changes fix the reported problem and preserve existing behavior.

- Reproduce repository bugs in Git-controlled, Docker-based environments.
- Develop Python/pytest harnesses, reference patches, and fail-to-pass/pass-to-pass checks.
- Review proposed fixes and tests for correctness, edge cases, and regression risk.
- Write rubric-based assessments with clear technical reasoning and reproducible test evidence.

**Public debugging example:** [MaintainOps login-throttling regression](https://github.com/Akrambadr99/maintainops/blob/main/tests/login-limits.test.ts) checks that successful sign-ins do not consume the failed-login allowance.

## Selected projects

Start with the implementation, then follow the tests that define its behavior.

| Project | What I built | Debugging and test evidence |
| --- | --- | --- |
| **[MaintainOps](https://github.com/Akrambadr99/maintainops)** | React, Express, and SQLite workflows for assets, work orders, inventory, and purchasing. | [Login-throttling regression](https://github.com/Akrambadr99/maintainops/blob/main/tests/login-limits.test.ts) · [Transaction rollback and restart recovery](https://github.com/Akrambadr99/maintainops/blob/main/tests/persistence.test.ts) |
| **[FactoryOS](https://github.com/Akrambadr99/FactoryOS)** | A TypeScript/Node.js material-reservation service with SQLite persistence and atomic batch releases. | [Competing updates and fault-injected rollback](https://github.com/Akrambadr99/FactoryOS/blob/main/server/releaseBatchHttp.test.ts) · [Restart and migration integrity](https://github.com/Akrambadr99/FactoryOS/blob/main/server/sqliteReservationStore.test.ts) |
| **[Taskora](https://github.com/Akrambadr99/Taskora)** | A React/TypeScript project workspace with an in-memory data layer, controlled network failures, and coordinated query state. | [Optimistic-update rollback](https://github.com/Akrambadr99/Taskora/blob/main/src/app/pages/BoardPage.test.tsx) · [Conflicts, duplicate submissions, and draft recovery](https://github.com/Akrambadr99/Taskora/blob/main/src/app/pages/IssueDetailPage.test.tsx) |
| **[Aegis Fleet Control](https://github.com/Akrambadr99/aegis-fleet-control)** | A fleet simulation connecting missions, resource reservations, scoped commands, and versioned browser persistence. | [Storage failures and stale writes](https://github.com/Akrambadr99/aegis-fleet-control/blob/main/src/storage/PersistentStorageAdapter.test.ts) · [Asynchronous validation races](https://github.com/Akrambadr99/aegis-fleet-control/blob/main/src/features/missions/ValidationRace.test.tsx) |
| **[Stratavera](https://github.com/Akrambadr99/AmberPath)** | Budget transfers and approval workflows with independent voting and immutable decision history. | [Approval-renewal regressions](https://github.com/Akrambadr99/AmberPath/blob/AmberPath/src/modules/approvals/renewal.test.ts) · [Persistence and evidence validation](https://github.com/Akrambadr99/AmberPath/blob/AmberPath/src/data/approval-renewal-persistence.test.ts) |
| **[CareRoster](https://github.com/Akrambadr99/CareRoster)** | Staffing and credential workflows with dependent approvals and role-specific revalidation. | [Credential changes and approval consistency](https://github.com/Akrambadr99/CareRoster/blob/main/src/staffing/coverage-matrix/shiftLedger.test.ts) · [Saved-data validation](https://github.com/Akrambadr99/CareRoster/blob/main/src/workspace/storageValidation.test.ts) |

*Stratavera is hosted in `AmberPath`. Several projects share foundation code and history. Each repository documents its current scope, setup, and implementation boundaries.*

## Debugging examples

**Login rate limiting — MaintainOps.** Successful sign-ins were consuming the shared-network failed-login allowance. The correction separates successful logins from failed attempts, with a regression test that checks both normal access and the throttling boundary. [Test](https://github.com/Akrambadr99/maintainops/blob/main/tests/login-limits.test.ts) · [Documented correction](https://github.com/Akrambadr99/maintainops/blob/main/docs/product-expansion.md)

**Atomic recovery — FactoryOS.** A failure while recording a batch-release receipt must not leave partially changed reservations or audit events. SQLite fault-injection tests check rollback, while competing-revision and restart/retry cases exercise conflict handling and duplicate-request safety. [HTTP and transaction tests](https://github.com/Akrambadr99/FactoryOS/blob/main/server/releaseBatchHttp.test.ts)

**Asynchronous UI conflicts — Taskora.** Revision conflicts, permission changes, and network failures can arrive while a user is editing. Regression cases check optimistic rollback, preserved drafts, duplicate-submission handling, and keyboard/focus recovery. [Issue-detail tests](https://github.com/Akrambadr99/Taskora/blob/main/src/app/pages/IssueDetailPage.test.tsx)

## Additional Python work

For a public Python example, [car-speed-estimation](https://github.com/Akrambadr99/car-speed-estimation) explores YOLOv8 detection, OpenCV video processing, vehicle tracking, and directional line-crossing counts. It is an experimental computer-vision project; its speed labels are not calibrated measurements.

## How I approach a bug fix

1. Reproduce the failure and establish the expected behavior.
2. Trace the relevant state, data, and authorization boundaries.
3. Implement a focused change and add a regression test.
4. Exercise failure paths and check that surrounding behavior still holds.
5. Explain the result with code, tests, and reproducible evidence.

## Toolbox

| Area | Technologies |
| --- | --- |
| Primary languages | Python, TypeScript |
| Python engineering | pytest, FastAPI, pandas, NumPy, automation scripts |
| Application development | React, Node.js, Express, SQLite, JavaScript, CSS |
| State and navigation | TanStack Query, React Router |
| Testing | Vitest, Testing Library, Playwright, regression and integration tests |
| Reproducible workflows | Git, GitHub Actions, Docker, npm, Vite, ESLint |

## A look inside

Application captures using local fixture data.

<details>
<summary><strong>MaintainOps · assets and maintenance execution</strong></summary>

[Explore the repository](https://github.com/Akrambadr99/maintainops)

![MaintainOps showing the site overview, work-order metrics, and maintenance status](assets/maintainops.png)

</details>

<details>
<summary><strong>Aegis Fleet Control · simulated robot operations</strong></summary>

[Explore the repository](https://github.com/Akrambadr99/aegis-fleet-control)

![Aegis Fleet Control showing the operations desk, facility map, robot status, and dispatch context](assets/aegis.png)

</details>

<details>
<summary><strong>Taskora · projects and team workflows</strong></summary>

[Explore the repository](https://github.com/Akrambadr99/Taskora)

![Taskora dashboard showing project counts and issue priorities; the app retains its Atlas Ops branding](assets/taskora.png)

</details>

<details>
<summary><strong>Stratavera · strategy and portfolio decisions</strong></summary>

[Explore the repository](https://github.com/Akrambadr99/AmberPath)

![Stratavera showing executive portfolio health, budget, risks, and the decision queue](assets/stratavera.png)

</details>

[Browse all repositories](https://github.com/Akrambadr99?tab=repositories)
