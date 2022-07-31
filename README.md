<h1 align="center">Get League Patch [Action]</h1>
<div align="center">
    An Action to grab the latest League of Legends patch from Data Dragon
</div>

## Usage

A patch string like `12.1` will be saved to an output variable named `patch`.

The action will fail if the patch info cannot be retrieved or seems invalid.

## Example

This will check for a new League Patch every day and create a PR to keep the badge in the `README` file up to date.

Note how the output variable is accessed via `${{ steps.yourStepId.outputs.patch }}`

```yaml
name: Update League Patch in README

on:
  schedule: [{ cron: '0 0 * * *' }]

jobs:
  update-badge:
    name: Update League Patch in README
    runs-on: ubuntu-18.04
    steps:
      - uses: actions/checkout@v3
        name: Check out current commit

      - id: yourStepId
        name: Get patch info
        uses: marvinscham/get-league-patch@v1.0.0

        # Replaces patch info with regex
      - name: Update patch in README shield
        run: sed -i "s/league%20patch-.*-brightgreen/league%20patch-${{ steps.yourStepId.outputs.patch }}-brightgreen/g" README.md
        shell: bash

      - name: Create Pull Request
        uses: peter-evans/create-pull-request@v4.0.4
        with:
          commit-message: Bump League Patch to ${{ steps.patch.outputs.patch }}
          title: Bump League Patch to ${{ steps.patch.outputs.patch }}
          body: This is an automated PR.
          branch: update-league-patch
```

_Derived from: [Action YAML](https://github.com/marvinscham/disenchanter/blob/main/.github/workflows/league-patch.yml)/[Repository/README](https://github.com/marvinscham/disenchanter)_
