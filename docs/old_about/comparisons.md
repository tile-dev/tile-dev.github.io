## **Hosted Jupyter Notebooks**

When data science teams want an end-to-end hosted environment for SQL and Python which enables collaboration and sharing, they may use a hosted Jupyter notebook.

Tile is not a replacement for the analysis or R&D stage of your data science process and seeks to be a complement to these platforms. Instead, it is only focussed on the 'last mile'. This means that you can also use Tile inside any existing Python environment, such as Colab, Deepnote, Hex, or SageMaker.

## **Realtime App Frameworks**

Frameworks such as Streamlit, Dash, and Gradio allow users to create realtime applications which you then deploy to the cloud.

### **Advantages**

- **Highly interactive**: reactive execution model better for highly-interactive use-cases (i.e. a live computer vision model)

### **Disadvantages**

- **Not decoupled**: You can only build realtime apps, not discrete reports (i.e. snapshots). This means that all sharing requires you [TODO: better explanation why this matters] 
- **Hard to migrate workloads:** Incompatible with Jupyter Notebooks and existing code, whereas Datapane can take existing notebooks and scripts with minimal configuration
- **Complex deployment and engineering:** requires architecting and handling of complex apps principles
- **No programmatic reporting: ** Doesn’t solve the JTBD around programmatic reporting or reporting embedded in workflows