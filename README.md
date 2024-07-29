# Export Branches action

A GitHub action that export all the branches in your current repository as a space delimited sting in the environment variable `$BRANCHES`.

## Inputs

## Inputs

### `github_token`

Your GITHUB_TOKEN.

## Example usage

```yaml
---
name: GitHub Action

on:
  - push

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: checkout
        uses: actions/checkout@v4
      - name: export branches
        uses: ucomesdag/export-branches-action@main
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
      - name: use branches
        run: |
          for branch in $BRANCHES; do
            echo $BRANCH
          done
        shell: bash
```
