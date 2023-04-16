Tile is an SDK and architecture for creating data-driven applications using Python. 

Tile aims to be the fastest and easiest way for data teams to share insights in a code-first way, with features such as:

- Static generation of 100% standalone HTML apps which don't require backends
- Serverless app-running with backend code execution through dynamic forms
- Plot and data components compatible with the majority of the Python data ecosystem (such as Pandas, Altair, Plotly)
- Built in client-side layout components, such as dropdowns, selects, grids
- Fully interactive datatables with exploration and export
- Integrates into existing Python environments, like Jupyter and Spark

## What can I build with Tile?

Tile shuns the idea that any app interaction requires a running backend server. Instead, the front-end and the backend are decoupled, similar to how many web frameworks and static-site generators work.

This is important because it means that you can create apps in various ways, depending on your use case:

1. Need to share ad-hoc plots and data from inside of a notebook? Using Tile, you can prerender an HTML single-page application, which doesn't even require a running server (like an interactive PDF!)
2. Want to build an automated dashboard which updates every five minutes? Add Tile to a GitHub Action or cron job to programmatically update your report on a cadence. 
3. Need your end users to enter parameters and generate results on-demand? Add forms to your report which execute your notebooks or scripts on the backend.

### Static reports

Tile allows you to generate static HTML reports from your existing environment, such as Jupyter, Airflow, or Spark. They are fully standalone and do not require a running Python server for viewing. Instead, you can export them as HTML reports or upload them to web-based hosts.

Views can contain components which wrap up the Python objects inside your analysis. Out of the box, you can add formats such as:

- Pandas DataFrames
- Plots from Python visualization libraries such as Bokeh, Altair, Plotly, and Folium
- Markdown and text
- General files, such as images, PDFs, JSON data, etc

Tile also provides a rich selection of layout and interactive components, such as grids, dropdowns, selects, and a fully interactive DataTable.

Views can replace creating a report in a BI tool, such as Looker or Tableau.

```python
import tile_dev as t
import snowflake.connector
from internal_lib import forecast

conn = snowflake.connector.connect(...)
users = conn.execute_query('get_users.sql').fetchall()
f_data, f_plot = forecast.predict(df)

sales_v_profit = alt.Chart(users).encode(x='sales', y='profit', color='category')

t.View(
    t.Plot(sales_v_profit, name='sale_v_profit'),
    t.DataTable(f_data, name='forecast_data'),
    t.Plot(f_plot, name='forecast_plot')
).save(path='report.html')
```

### Data apps

#### Introduction

Static reports are great to start with. They are portable, scalable, and fast to create.

But eventually you might need your end-users to be able to _run_ your Python script or Jupyter Notebook themselves. 

Expanding on the above example, we can add a dynamic form to our view which users can run with parameters.

```python title='analysis.ipynb'
# API TBD - this is a mock!
import tile_dev as t
import snowflake.connector
from internal_lib import forecast

conn = snowflake.connector.connect(...)
users = conn.execute_query('get_users.sql').fetchall()

sales_v_profit = alt.Chart(users).encode(x='sales', y='profit', color='category')

t.View(
    t.Plot(sales_v_profit, name='sale_v_profit'),
    t.Form(id='forecast', params={'days' : 'integer', 'item': 'string'})
    t.DataTable(f_data, name='forecast_data'),
    t.Plot(f_plot, name='forecast_plot')
).Backend(
    t.Function(path='./forecast.py', id='forecast')
).run_app()
```

```python title='forecast.py'
# API TBD - this is a mock!
import tile as t
from internal_lib import forecast

days = t.Params('days')
item = t.Params('items')

f_data, f_plot = forecast.predict(df, item, days)

t.View(
    t.DataTable(f_data, name='forecast_data'),
    t.Plot(f_plot, name='forecast_plot')
)
```

## What is Tile not?
- Tile is not a realtime reactive web framework like Streamlit or Dash
- Tile is not an analysis environment like Jupyter
