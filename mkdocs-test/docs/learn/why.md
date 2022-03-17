
## Why does Tile exist?

We believe the future of data analysis is open-source and code-first. Data teams are increasing choosing developer-first tools over UI-based platforms.

But there is one part of the stack that has very little developer-first tooling: the front-end. We believe the front-end is fundamentally broken because it's currently bundled into big, expensive BI tools. Even though many data scientists do their analysis in a code-first platform, and are forced to move to a propietary UI-based platforms when its time to share.

If you've enjoyed the benefits of developer-first tooling, this is a problem:

1. Many modern data use-cases don't fit into the BI paradigm, which is optimized for providing a simple lense on the data warehouse. 
2. Having the BI tool as the sole view-layer adds a high fixed cost to data science results. Often data scientists will build everything in Python, only to find they have to transpose it all to a BI tool when they want to share.
3. Data teams often need to process data which is not in the central warehouse. Maybe they want to build an app directly on Stripe or Marketo. In this case, they have to go to third-party SaaS tools and ditch the data team entirely
4. Modern reporting needs to be programmatic. Instead of a filter on a view, end-users often need a set of different reports with completely different components; for instance, to create a custom external report for each of their clients.


## What value does it provide?

#### Code-first
Tile is code-first, which means that you have all of the benefits of versioning, testing, and collaboration which are absent in UI-first tools. It also makes it simple to create reports programmatically.

#### Simple and fast
Tile lets you build and share reports in under 5 lines of code.

#### Limitless applications
Tile lets you to turn Jupyter notebooks and scripts into full-blown applications which take parameters. This unlocks data teams to provide 

#### Integrates with your stack
Tile allows you to generate and share reports from inside of wherever you already analyze data. You can immediately use tile inside of PySpark, Airflow, Jupyter, Colab, or Sagemaker.

#### Performance
Tile's serverless infrastructure allows it to scale.

#### Maximum compatibility
Tile renders the libraries you already use, like Pandas, Plotly, and Altair. The goal of the project is to have maximum compatibility with the rest of the data science ecosystem.

Tile's runner is optimized to be compatible with existing Python scripts and Jupyter notebooks, without requiring users to rewrite existing code.

#### Serverless
Not all use-cases should require running a server in the cloud.

Tile believes in a separation of the presentation layer and execution layer. Tile views are compiled into interactive static pages which you can share as HTML documents. When building an app, execution happens in a serverless fashion.
