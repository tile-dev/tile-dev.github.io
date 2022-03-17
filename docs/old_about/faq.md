### Is Tile production ready?
Tile is a repackaging of what was previously Datapane's internal reporting library, which has served millions of reports to hundreds of thousands of people. 

### Who builds Tile?
Tile is an open-source community library which is open to contributions, but is most actively developed by the Datapane team.

### Is Tile free?
Yes, Tile is free and will forever be free. 

### When should I not use Tile?

#### Realtime apps
Tile's execution model is serverless and based on request-response. If you want realtime apps (where you drag a slider and see updates in realtime, without hitting a submit button), Tile isn't currently a great fit. In this case, we'd recommend something like Streamlit or Dash.

#### Classic BI
If you are just computing some simple KPIs on a data warehouse and not doing anything programmatic, you may be better served by SQL and your regular BI tool.

#### No-code
If you want non-technical people to build reports who want to use a drag-and-drop UI, Tile isn't the right fit.