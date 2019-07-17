# Schema Reference

This page provides reference information on publishing to the 360Giving Data Standard and assumes some technical knowledge. If you are just getting started with the 360Giving data standard you may wish to consult the [Publish Your Data](http://www.threesixtygiving.org/data/publish-data/) pages on the 360Giving website.

The standard is maintained using JSON Schema although it may be published in [other formats](templates-csv.md).

In this section you will find:

* a reference for each section of the schema which provides guidance for its use
* a full representation of the 360Giving schema itself.

If you are a publisher looking for advice on using our spreadsheet template please consult our [guidance on spreadsheets](guidance.md).



## Data formats

There are two main formats available for representing 360Giving data.

1. **Spreadsheet**

   Data placed in a spreadsheet can make use of easy to read, user-friendly **column titles**, and is ideal for recording one grant per row. This is the most common format that publishers choose. More complex representations of data can also be reported if required.

2. **JSON**

   Data in JSON format is ideal for direct use by developers building visualisations and web apps. The JSON should conform to the [360Giving JSON Schema](360giving-json-schemas). Anyone automating the publication of their data from their internal databases or via an API may favour this format. The column titles used in spreadsheet representations of data are derived directly from the [360Giving JSON Schema](360giving-json-schemas).

The [360Giving Data Quality Tool](https://dataquality.threesixtygiving.org/) can be used to convert data between these formats, providing structured data for developers, and spreadsheet simplicity if you want to browse, sort and filter data on your desktop.

## JSON format

The 360Giving standard is defined by a [JSON Schema](http://json-schema.org/), which details the entities that can be described using the standard, and the properties it recognises.

At the root of the data model is a 'grant'. Grants have a number of direct properties (e.g. Title, Description, Currency, Amount Awarded etc.) and then a number of related entities, including Organisations (Funder and Recipient), Locations (Recipient, Beneficiary), Classifications, Grant Programmes, and Transactions.

```eval_rst
.. _360giving-json-schemas:
```

### 360Giving JSON Schemas
The 360Giving JSON Schemas are the authoritative source of information about the standard, and it should always be possible to transform 360Giving data into structured JSON data according to these schema.

The <a href="../_static/360-giving-schema.json">360Giving Grant Schema</a> defines the structure of an individual 'grant' and the documentation from this is displayed below, or <a href="../_static/docson/index.html#../360-giving-schema.json">fullscreen here</a>.

When exchanging data about a single grant or any number of grants, those grants need to be packaged into a single JSON file. The <a href="../_static/360-giving-package-schema.json">360Giving Package  Schema</a> describes how grants are packaged into one file.

In general, most publishers will initially only use a sub-set of the possible features of the standard, but it is designed to accommodate comprehensive data about all stages of a grant process: for a full 360-degree view.

<div style="height:400px; overflow:auto; border:1px solid grey;">
<script src="../_static/docson/widget.js"
        data-schema="../360-giving-schema.json">
</script>
</div>

### Field names and titles

Each entity, property and relationship in the schema has both a machine-readable field name and an English language title (apart from Transactions).

The English language titles are important for humans working to make sense of the data in everyday desktop software, and so the Spreadsheet Template and the documentation above makes use of titles as opposed to field names.

The field names are important for computers reading the data, and even if other language titles are provided in future, the underlying field names will remain constant.

A mapping between column titles and field names is given below:

```eval_rst
.. jsonschema-title-fieldname-map:: ../schema/360-giving-schema.json
```

### JSON

When data is being generated directly out of a database system, publishers should consider using the JSON schema to provide a JSON file.

Developers may also wish to build their applications of JSON versions of the data.

The [360Giving Data Quality Tool](https://dataquality.threesixtygiving.org/) supports round-tripping of data between the Spreadsheet Template and JSON representations.
