---
title: Privacy Policy — Datadesk for Jira
---

# Privacy Policy

**DataForte AB** · Tant Gröns väg 54, 147 60 Uttran, Sweden
Contact: hello@dataforteab.com
Last updated: 17 August 2026

This policy describes how the Atlassian Marketplace app **Datadesk for Jira** ("the app") handles
data. The app is built on Atlassian Forge and runs on Atlassian's infrastructure.

## What the app does with your data

Datadesk turns data-pipeline failures into tracked Jira work. It **receives** webhooks and creates
Jira issues; it makes **no outbound calls** to dbt Cloud, Databricks, Airflow or any other system.
It processes:

- **Job event metadata** from the webhook you configure: job id and name, run id, run status,
  environment, project name, the link back to the run, and the failure reason your tool supplies.
- **Jira issue data** needed to create and update issues: project key, issue type, issue key, and
  the comments the app itself writes.
- **Configuration you enter**: routing rules (job tag → Jira project, issue type, priority,
  assignee, labels, mute list) and an optional shared webhook secret.

The app collects no analytics, does not profile users, and does not sell or share data with anyone.
DataForte AB has no access to your Jira site or your data platform.

## Where data is stored

All app data lives in the **Forge Key-Value Store**, inside Atlassian's cloud infrastructure, scoped
to your installation. DataForte AB operates no servers and stores no copy of your data.

| Data | Purpose |
|---|---|
| Routing rules | deciding which jobs create issues in which Jira project |
| Shared webhook secret | rejecting deliveries that do not carry it — stored **encrypted** in Forge secret storage |
| Link index (job identity ↔ Jira issue key, repeat count, timestamps) | deduplicating repeat failures onto one issue and closing it on recovery |
| Job snapshot per linked Jira issue (title, status, environment, run URL) | rendering the Pipelines panel without calling out |

## Data sent outside Atlassian

**None.** Datadesk has no external egress: it does not call dbt Cloud, Databricks, Airflow or any
third-party service. Data flows one way — your tool posts to the app's webhook URL, and the app
writes inside your own Jira site.

## Personal data

The app does not intentionally process personal data. Two indirect cases are worth naming:

- A failure message from your pipeline may contain personal data if your own systems put it there.
  The app copies that text into a Jira issue in your own site.
- If a rule assigns issues to a Jira user, that user's Atlassian account id is stored in the rule.

DataForte AB acts as a data processor for whatever passes through the app; you remain the
controller. There are **no sub-processors**: nothing leaves Atlassian's infrastructure.

## Legal basis for processing

Where the GDPR or UK GDPR applies, we process data on two bases: to **perform the contract** under
which the app is provided to you (Art. 6(1)(b)), and the **legitimate interest** (Art. 6(1)(f)) you
and we share in operating the integration you configured — creating, deduplicating and closing
issues — which cannot be achieved less intrusively, because the app handles only the data those
functions require. As processor we act on your documented instructions as controller.

## International transfers

Data is stored and processed within your Atlassian Cloud tenant, in the region Atlassian assigns to
it. The app introduces **no cross-border transfer of its own**, because it sends nothing outside
Atlassian.

## Retention and deletion

Data lives for as long as the app is installed. **Uninstalling the app deletes its Forge storage**,
including the encrypted webhook secret. Jira issues the app created remain in your Jira site,
because they are your issues.

To request information or deletion at any other time, write to hello@dataforteab.com. We answer
within 30 days.

## Your rights

Under the GDPR you may request access to, correction of, or deletion of personal data, and you may
lodge a complaint with the Swedish data protection authority (Integritetsskyddsmyndigheten).

## Security and incident notification

The shared webhook secret is held in Forge **encrypted secret storage** and is never returned to the
admin UI or written to logs. Requests that do not carry the configured secret are rejected. Because
the app stores data only inside your Atlassian tenant, a breach of that stored data would be an
Atlassian platform event handled under Atlassian's incident process; where we become aware of an
incident affecting data the app processes, we will notify you at the vendor contact on your
installation without undue delay.

## Children

The app is a business tool for data and software teams. It is not directed to children, and we do
not knowingly process children's data.

## Changes

Material changes to this policy will be published on this page with a new "last updated" date.
