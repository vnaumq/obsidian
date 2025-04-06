[[Data Modeling]]

In [computing](https://en.wikipedia.org/wiki/Computing "Computing"), the **star schema** or **star model** is the simplest style of [data mart](https://en.wikipedia.org/wiki/Data_mart "Data mart") [schema](https://en.wikipedia.org/wiki/Logical_schema) and is the approach most widely used to develop data warehouses and dimensional data marts. The star schema consists of one or more [fact tables](https://en.wikipedia.org/wiki/Fact_table "Fact table") referencing any number of [dimension tables](https://en.wikipedia.org/wiki/Dimension_\(data_warehouse\) "Dimension (data warehouse)"). The star schema is an important special case of the [snowflake schema](https://en.wikipedia.org/wiki/Snowflake_schema "Snowflake schema"), and is more effective for handling simpler queries.

The star schema gets its name from the [physical model's](https://en.wikipedia.org/wiki/Physical_data_model "Physical data model")[[3]](https://en.wikipedia.org/wiki/Star_schema#cite_note-Date-IntroToDBMS-3) resemblance to a [star shape](https://en.wikipedia.org/wiki/Star_polygon "Star polygon") with a fact table at its center and the dimension tables surrounding it representing the star's points.

## Model

The star schema separates business process data into facts, which hold the measurable, quantitative data about a business, and dimensions which are descriptive attributes related to fact data. Examples of fact data include sales price, sale quantity, and time, distance, speed and weight measurements. Related dimension attribute examples include product models, product colors, product sizes, geographic locations, and salesperson names.

## Benefits

Star schemas are [denormalized](https://en.wikipedia.org/wiki/Database_normalization "Database normalization"), meaning the typical rules of normalization applied to transactional relational databases are relaxed during star-schema design and implementation. The benefits of star-schema denormalization are:

- Simpler queries – star-schema join-logic is generally simpler than the join logic required to retrieve data from a highly normalized transactional schema.
- Simplified business reporting logic – when compared to highly normalized schemas, the star schema simplifies common business reporting logic, such as period-over-period and as-of reporting.
- Query performance gains – star schemas can provide performance enhancements for read-only reporting applications when compared to highly [normalized](https://en.wikipedia.org/wiki/Database_normalization "Database normalization") schemas.
- Fast aggregations – the simpler queries against a star schema can result in improved performance for aggregation operations.
- Feeding cubes – star schemas are used by all [[OLAP]] systems to build proprietary [[OLAP ]]cubes efficiently; in fact, most major OLAP systems provide a [[ROLAP]] mode of operation which can use a star schema directly as a source without building a proprietary cube structure.