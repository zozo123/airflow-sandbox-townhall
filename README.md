# New Sandbox provider for ephemeral task isolation

Slides for my talk at the **Apache Airflow Monthly Virtual Town Hall — July 10, 2026**.

**▶ View the slides:** https://zozo123.github.io/airflow-sandbox-townhall/

Navigate with **←/→** (or click / swipe), press **`f`** for fullscreen. `#N` in the URL deep-links to slide N.

## What the talk is about

Running each Airflow task try in an **ephemeral microVM sandbox** — created for the try, destroyed when it ends. The talk frames two use cases behind the same primitive:

- **Fast fan-out/fan-in:** start many hot task computers in milliseconds, collect results, and delete them.
- **Controlled untrusted execution:** run AI-written, tenant-written, or partner code off the worker with scoped network and secret access.

- **PR:** [apache/airflow#68847](https://github.com/apache/airflow/pull/68847) — `SandboxExecutor`, `SandboxOperator`, `@task.sandbox`, with pluggable backends (local, Daytona, E2B, Modal, islo)
  - **Update (Aug 2026):** #68847 was reworked and merged on 2026-08-13 as `SandboxToolset` in the `common.ai` provider; the standalone executor lives at https://github.com/zozo123/airflow-provider-sandbox.
- **Issue:** [apache/airflow#68845](https://github.com/apache/airflow/issues/68845)
- **Discussion:** [dev@airflow.apache.org](https://lists.apache.org/list.html?dev@airflow.apache.org) — following maintainer feedback, the work is pivoting into the `common.ai` provider as a `SandboxToolset`

The deck is a single self-contained `index.html` — no build step, no framework.

— [Yossi Eliaz](https://yossieliaz.netlify.app/), Incredibuild · more writing at https://zozo123.github.io/
