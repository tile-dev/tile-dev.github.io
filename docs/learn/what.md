Tile is an SDK and architecture for creating data-driven applications. You can use it to create static documents (such as reports), automated dashboards, or parameterized apps which run in the cloud. 

Tile aims to be the fastest and easiest way for data teams to share insights in a code-first way, with features such as:

- Static generation of standalone HTML reports
- Serverless app-running with parameters 
- Plot and data components compatible with the majority of the Python data ecosystem (such as Pandas, Altair, Plotly)
- Built in client-side report components, such as dropdowns, selects, and interactive datatables
- Fully integratable into existing Python environments, like Jupyter and Spark

## What isn't Tile?
- Tile is not a realtime reactive web framework like Streamlit or Dash
- Tile is not an analysis environment like Jupyter

## What can I build with Tile?

### Static reports

Tile allows you to generate static HTML reports from your existing environment, such as Jupyter, Airflow, or Spark. They are fully standalone and do not require a running Python server for viewing. Instead, you can export them as HTML reports or upload them to web-based hosts.

Views can contain components which wrap up the Python objects inside your analysis. Out of the box, you can add formats such as:

- Pandas DataFrames
- Plots from Python visualization libraries such as Bokeh, Altair, Plotly, and Folium
- Markdown and text
- General files, such as images, PDFs, JSON data, etc

Tile also provides a rich selection of layout and interactive components, such as grids, dropdowns, selects, and a fully interactive DataTable.

Views can replace creating a report in a BI tool, such as Looker or Tableau.

#### Example

```python
import pandas as pd
import tile-dev as t

df = ...

t.View(t.DataTable(df)).save_report(path='report.html')
```

### Data apps

#### Introduction

Static reports are great to start with, but you might need your end-users to be able to run your Python script or Jupyter Notebook themselves. 

Tile allows you to turn any Python script or Notebook into an API which can be called from inside your views. 
Need your report to 

Tile
Tile's Runner makes it simple to deploy a script or Jupyter Notebook so that end-users can run it with parameters. You can combine it with Views to create interactive data apps.

Runner is an open standard for defining how your data science code should run and what parameters it takes. It's execution is serverless, which means for each request, it spins up a docker container, executes the workload, and shuts down.


#### Example

```yaml
script: calculator.ipynb
name: startup_calculator
repo: https://github.com/datapane/gallery/tree/master/startup-calculator
title: Startup Burn Calculator 
parameters: 
  - name: current_cash
    description: The amount of cash you have in the bank
    type: integer
    required: True
    default: 100000
    min: 0
  - name: forecast_length_years
    description: The number of years to forecast
    type: integer
    required: True
    min: 1
    max: 10
    default: 2
```

```bash
$ tile runner exec
[-] Building startup_calculator...
```