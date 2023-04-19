---
title: Tile by Datapane - The SDK for creating data apps
hide:
  - navigation
  #- toc
---
# Welcome to Tile!

Tile is an open-source framework for building end-to-end data products using Python. It offers a complete **data stack in a box** which provides everything you need to ship an internal data product or tool for non-technical users. 

## Why use Tile?

* Build robust data products for business units with minimal DevOps or infrastructure resource
* Leverage the best data tooling out of the box in minutes, without organizational change and investment
* Replace clunky BI tools with interactive data products built using Python and open-source
* Replace expensive external point solutions and vendors with in-house apps built using Python
* Cut the time to create a data product from 15 people to 1 person

## How it works

Tile provides the entire data stack of an analytics product, from web apps, reporting, OLAP, ETL, and notifications, in a single format. Tile is infrastructure as code, with all components defined and configured in Python.

See [Architecture](./architecture.md) for more information.

This entire stack is defined as code in a single Python file, such as this one:

```python
from tile.package import Package

package = Package(
  entrypoint = "app.py",
  databases = [
     DuckDBConnector(),
  ],
  # scheduled tasks
  schedules = [
      Task(name="daily-report", cron="00 9 * * MON-FRI"),
  ],
  # notification configuration, e.g. Slack, Email. Teams
  notifications = [
    Email(smtp_config = ""),
    Slack(slack_api_key = ""),
  ],
  # ELT workflows
  workflows = [
    Workflow(name="Load HR Info", cron="00 1 * * *", 
             source="Workflow", on_load="transform-hr-info")
  ]
)
```

When you can build and run on Tile. Tile handles the full application lifecycle, including the deployment and running of Tile Apps.

## Features

- Building, deploying, and running full-stack data applications
- Securely manage authentication and access control
- Export and embed standalone reports
- Integrate data from existing DBs and third-party platforms into a virtualised data layer
- Run scheduled backend processing, such as data transformations or automated reports
- Surface insights and reports via Slack or Microsoft Teams

