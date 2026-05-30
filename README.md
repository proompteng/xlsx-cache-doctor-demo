# XLSX Cache Doctor demo

This repository is a small, live proof for the [XLSX Cache Doctor](https://github.com/marketplace/actions/xlsx-cache-doctor) GitHub Action.

The demo pull request adds a tiny workbook with one deliberately stale cached formula value:

- `Sheet1!A61` is `60`.
- `Sheet1!B61` contains `=A61*10`.
- The workbook cache stores `999` for `Sheet1!B61`.
- The recalculated value is `600`.

The workflow uses `proompteng/bilig@v1` in report-only mode, checks that the Action found exactly one stale cached formula value, and uploads the JSON report as an artifact. It does not need Excel, LibreOffice, browser automation, secrets, write permissions, or a PR comment bot.

Use this repo when you want to inspect the Action as a GitHub reviewer would: pull request, check summary, step outputs, and downloadable JSON artifact.

Main project: https://github.com/proompteng/bilig
