# Shared Workflows

> Shared [Reusable GitHub Workflows](https://docs.github.com/en/actions/learn-github-actions/reusing-workflows#overview) for my projects

## Usage

To use the shared workflow, you need to use the `uses` keyword when referring to a `job` in the workflow. As an example: `jobs.<job_id>.uses`.

Here is an example workflow file:

```yaml
name: Publish NPM Package

on:
  push:
    branches:
      - main
  workflow_dispatch:

jobs:
  npm-publish:
    uses: devshareacademy/shared-workflows/.github/workflows/publish-package.yml@v1.0.0
    secrets:
      npm_token: ${{ secrets.NPM_TOKEN }}
      gh_token: ${{ secrets.GH_TOKEN }}
```

*Note:* For more information on calling a reusable workflow, please see the following: [Calling Reusable Workflows](https://docs.github.com/en/actions/learn-github-actions/reusing-workflows#calling-a-reusable-workflow).
