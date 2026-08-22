---
title: Datadesk for Jira
---

# Datadesk for Jira

Data pipeline failures become tracked Jira work: auto-created, deduped, and closed when the job
succeeds again.

An Atlassian Forge app by **DataForte AB**, available on the Atlassian Marketplace.

## What it does

- A pipeline job fails in dbt Cloud, Databricks, Airflow or any tool that can send a webhook, and a
  Jira issue is created with the job name, the environment and a link back to the run.
- The same job failing again comments on the existing issue instead of filling your backlog with
  duplicates, because the dedup identity is the job, not the run. A nightly job that fails five
  nights running is one issue with five comments.
- The next successful run of that job closes the Jira issue and posts a recovery note, so the
  board reflects reality without anyone tidying up after it.
- Rules per pipeline decide the target Jira project, the issue type, the assignee and which jobs
  are muted entirely.
- A Pipelines panel appears only on linked issues, and an hourly reconciliation scan picks up
  anything a dropped webhook would have lost.

## Pages

- [Support](support.html)
- [Privacy Policy](privacy.html)
- [Terms of Service](terms.html)

---

DataForte AB · Tant Gröns väg 54, 147 60 Uttran, Sweden · hello@dataforteab.com
