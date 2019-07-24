# Schema Reference

This page provides reference information on publishing to the 360Giving Data Standard and assumes some technical knowledge. If you are just getting started with the 360Giving data standard you may wish to consult the [Publish Your Data](http://www.threesixtygiving.org/data/publish-data/) pages on the 360Giving website.

> If you are a publisher looking for advice on using our spreadsheet template please consult our guidance on [guidance on spreadsheets](../guidance/spreadsheets).

The 360Giving standard is defined by a [JSON Schema](http://json-schema.org/), which details the entities that can be described using the standard, and the properties it recognises. The 360Giving JSON Schemas are the authoritative source of information about the standard, and it should always be possible to transform 360Giving data into structured JSON data according to these schema. As of writing, most publishers currently publish using one of the [spreadsheet templates](../guidance/spreadsheets) which are derived from the JSON Schema and may be converted to JSON using either the [360Giving Data Quality Tool](https://dataquality.threesixtygiving.org/) or the general-purpose [flatten-tool](https://flatten-tool.readthedocs.io/en/latest/).

At the root of the data model is a 'grant'. Grants have a number of direct properties (e.g. Title, Description, Currency, Amount Awarded etc.) and then a number of related entities, including Organisations (Funder and Recipient), Locations (Recipient, Beneficiary), Classifications, Grant Programmes, and Transactions.

The <a href="../_static/360-giving-schema.json">360Giving Grant Schema</a> defines the structure of an individual 'grant' and the documentation from this is displayed on the [360Giving Schema Reference page](./schema), or <a href="../_static/docson/index.html#../360-giving-schema.json">fullscreen here</a>.

When exchanging data about a single grant or any number of grants, those grants need to be packaged into a single JSON file. The <a href="../_static/360-giving-package-schema.json">360Giving Package Schema</a> describes how grants are packaged into one file.

In general, most publishers will initially only use a sub-set of the possible features of the standard, but it is designed to accommodate comprehensive data about all stages of a grant process: for a full 360-degree view.

In this section of the documentation you will find: a reference for the 360Giving Grant schema and its sections which provide some technical guidance on its use; and a reference for the 360Giving Grant Package schema which grants should be used to distribute grants and provides fields for adding metadata.


```eval_rst
.. toctree::
   :maxdepth: 2

   schema
   package-schema
   reference
   identifiers

```
