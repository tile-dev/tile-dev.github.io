# Architecture & Philosophy

Tile's architecture takes inspiration from web frameworks and static site generators.

#### Decoupled

Tile is multi-tier architecture where the view layer and execution layer are decoupled. 

This has obvious performance benefits (as reports can scale to an unlimited number of users). It also means that asset and report generation can happen inside of other platforms you already use - like Spark and Jupyter. 

![Architecture-1](/assets/architecture-1.png)


#### Static generation

Reports in Tile are statically generated. They can be exported as HTML files which can shared without a running server, or uploaded to a compatible web host, such as Datapane.
 
#### Serverless

Tile's execution model allows you to build automated reports (that update on a schedule), or you can add superpowers to your reports by turning them into apps which can be run with parameters.

![Architecture-2](/assets/architecture-2.png)
