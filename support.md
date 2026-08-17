---
title: Support — Datadesk for Jira
---

# Support

**Datadesk for Jira** is built and supported by **DataForte AB**.

- **Email:** hello@dataforteab.com
- **Language:** English
- **Hours:** Swedish business days, 09:00–17:00 CET
- **First response:** within two business days

## Before you write

Most problems fall into one of these:

**No Jira issues are being created.** Check in order: the webhook URL from the app's admin page is
pasted into your tool (dbt Cloud -> Account settings -> Webhooks, subscribed to **job.run.errored**
*and* **job.run.completed**; Databricks -> job notification destination with on_failure and
on_success; Airflow -> on_failure_callback); a routing rule matches the job's tags, or a catch-all
rule (`*`) exists; and the subscription is active.

**Issues are created but never close.** The recovery event is missing. dbt Cloud only sends
`job.run.completed` if you subscribed to it, and Databricks needs `on_success` as well. Anything
else can post `{"job":"...","status":"success"}` or append `&status=success` to the URL.

**One job opens many issues.** The dedup identity is the job id (dag/task for Airflow). If your
sender changes that id between runs, every run looks like a new job — send a stable identifier.

**A failing job floods the backlog.** It should not: repeat failures comment on the open issue. If
you see duplicates, the incoming job id is changing, or two different senders describe the same job
under different ids.

When you write, include your Jira site URL, the job or table name, and roughly when it happened —
that is usually enough to find it in the logs.

## Links

- [Privacy Policy](privacy.html)
- [Terms of Service](terms.html)
