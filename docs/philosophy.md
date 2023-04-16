---
#title: The Tile by Datapane - The SDK for creating data apps
hide:
  - navigation
---

The design of Tile is based around our, quite specific, ideas of how to build modern data applications that takes advantage of upcoming trends in the data and infrastructure space. Much of this is in opposition to the large-scale,  distributed, Big Data and micro-services-heavy "Modern Data Stack" that we believe simply results in over-complex, fragile and over-engineered systems that very often don't actually provide value to their users or stakeholders.

### Single-node over multi-node

Single node machines are *really* fast and just getting faster, yet tools like Spark turn all data processing issues into multi-node concerns. 
We think that as the core-counts increase and as tooling becomes more sophisticated, e.g. DuckDB and Apache Arrow,  this tradeoff no longer makes sense for many traditional enterprise use-cases.
The limits of what are possible on a single node machine, or even a developer laptop, are becoming far larger and can fit within a single node. Moving to multiple nodes drastically decreased latency whilst increasing the range of potential issues.


Similar issues occur on the application side, where the general wisdom when building a complex data product with many endpoints, tasks, and integrations would be to use a tool like Kubernetes. However again we bleive that for an internal enterprise use-case, it is much simpler and more rleibale to use a fast, ,ulti-core single node machine along with more lwo-maintence deployment solutions like Docker.


For Tile's on-prem and enterprise hosted options, we believe that as providing a single-node VM per customer is the right approach here, in terms of isolating a customer's data, performance, relaiblity and ease of mainaince and upgrading. 


### The Modern Data Stack is overkill

We don't believre that the "modern Data Stack" comprpsied of loading large amounts of data into Data Warehouses and Data Lakes like Snowflake or Redshift, then using tools liike `dbt` and dsibtruted processors like Spark, are at all suitable for all domains and scales.

For most enterprise use-cases, especically for intnerall tooling that Tile is aimed at, for isntacne Marketing Analytics, HR Analytics Developer Analytics and more, the datasets incovled can fit within a single machine and we cnan utilise a much simpler and more reliable set of technologies, like DuckDB, polars, pandas, and more.

This is much simpler to manage and maintain, whilst still being faster for the interendded use-cases.


### Python is the lingua franca for data analysis

There are many languages that can be used for data analytis, such as R, Matlab, Juila, Scala and more - however we belive that Python is uniquely positioned to be the common language used for all data related tasks in the near-mid future.

Functionally as a glue-code, the size of the community and strength of the ptghon eco-sshytem means that there are libraries and tools work with all the core data analytics tasks, including libraries like Padnas, Polars, DIEs like Jupyter, and librraries tow work with ML, cloud infrasutrvture, SaaS APIs and more.

BI tools based on SQL, such as Tableau, simpley don't have the power, ecosystem, or flexibilty to provide what is needed for modern companies to stay ahead.


### A Data Application Layer is not enough

There are many tools for building "data apps" in Python to provide intereactive plots and tables, such as Streamlit, Dash, Voila, and others.

We believe that tools like Streamlit are great for quickly building demos and generating "Interactive Powerpoints" by the data team to demo to stakeholders. However we've ofound they they are often of temporary use only at the time and are not maintined or used after. We've found that they are missing many features that make them not capable of forming the basis of fully-featured internall data products.

At Tile we have built Datapane, which is a really simple, Raeact and HTMX-inspired data application framework that also provide a way to build reports, dashboards, and reusable components that can all be combined together to build interacte data driven applciuations driectly in Ptyhon and Jupyter without requireing any Javascript. Datapane support a wide range of features required by product-greade data projects, including background tasks, integrated analytics databases, and user / permissions support.

The Tile data stack  uses the Datapane Server framework to support Python analytics code, 

The Datapane server framework is a large and important part of the Tile data stack, wich  when combined with the other components in the sytem, allows you to easily build, deploy and run enterprise reasy interal data applications rahter than demos and "Interactive Powerpoints".

