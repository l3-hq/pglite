The package workflow runs on GitHub-hosted Ubuntu runners. WASM builds, Node test matrices, dependent packages, demo builds and artifacts remain required by the final Check job.

Netlify deployment and npm publishing run only in the upstream repository. Fork builds still produce and validate the website and demos without publishing to upstream accounts.

Install dependencies with `pnpm install --frozen-lockfile`, enable the repository hooks with `mise run setup-hooks`, and run `mise run check` before pushing. The gate checks workflow syntax, shell commands and runner routing; CI runs the package builds and tests.

The routing audit derives from laith-page/migrate commit 208b86d, adapted for GitHub-hosted runners and Node.js.
