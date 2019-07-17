# Publishing using spreadsheets
To produce 360Giving data in a spreadsheet, it is possible to start with an empty spreadsheet and construct the column titles (and any additional sheets), using the information given below. However, for many people, the starting point is the spreadsheet template described below.

## Excel (.xlsx)
For convenience we provide a <a href="../_static/summary-table/360-giving-schema-titles.xlsx">360Giving Spreadsheet Template</a> that can be used directly, or adapted to your needs.

The template is a multi-sheet spreadsheet, and each sheet is described below.

Many data producers will be able to fit all the information about a single grant on one row of a spreadsheet. In fact most data producers do exactly that, and provide a single sheet with many individual grants.

Where data producers have more complex information, for example where a grant has many beneficiary locations, we call this a [One to many relationship](one-to-many-relationships).
Information about how to create data with [One to many relationships](one-to-many-relationships) is described below.

The 360Giving Spreadsheet template consists of a 'grants' sheet which contains the most common data fields.

The [Additional fields](additional-fields) section provides details of all other possible fields that can be reported. (These are derived from the [360Giving JSON Schema](360giving-json-schemas) ).

### Grants Sheet

The main 'grants' sheet includes sections for:

* Basic information about the grant;
* Planned dates for the grant;
* Planned dates of the activity;
* Details of the recipient organisation;
* Details of the funding organisation;
* The location of beneficiaries;
* Details of the grant programme funding is from;

```eval_rst
.. jsonschema-titles:: ../schema/360-giving-schema.json
```

```eval_rst
.. _additional-fields:
```

### Additional fields

The main 'grants' sheet only includes the most common information used by most data publishers. For many people this is enough.

The other sheets in the <a href="../_static/summary-table/360-giving-schema-titles.xlsx">360Giving Spreadsheet Template</a> provide the details of all the possible fields that can be reported. These sheets serve a dual purpose:

1. As a way to add more information to our 'grants' sheet

   The column titles in the extra sheets provide a handy mapping from the JSON Schema to a more human readable form, showing us all of the possible fields available in the 360Giving Data Standard.

   You can use any of these column titles on your main 'grants' sheet if you wish.

2. As a way of providing information about [One to many relationships](one-to-many-relationships)

If, when creating your data, you only need a few additional fields from the additional sheets, you can simply copy them from one sheet to another.

If you have additional data to report that does not fit any of the columns provided in the spreadsheet, it is okay to create your own column titles in order to report it.

```eval_rst
.. hint:: **Naming your own columns.**

  If you are adding your own column titles it is best to use simple titles and to avoid special characters which could cause problems in data reuse.

  Using only lowercase and uppercase alphabetical characters (``a-z`` and ``A-Z``), numerical digits (``0-9``), colons (``:``), parentheses (``(`` and ``)``) and single spaces will help to avoid problems. Full-stops (``.``) are known to cause issues and should be avoided. Other characters could be used, but haven't been fully tested in all possible situations.
```

#### Actual Dates

```eval_rst
.. jsonschema-titles:: ../../schema/360-giving-schema.json
    :child: actualDates
```

#### Planned Dates

```eval_rst
.. jsonschema-titles:: ../schema/360-giving-schema.json
    :child: plannedDates
```

#### Funding Org

```eval_rst
.. jsonschema-titles:: ../schema/360-giving-schema.json
    :child: fundingOrganization
```

#### Recipient Org

```eval_rst
.. jsonschema-titles:: ../schema/360-giving-schema.json
    :child: recipientOrganization
```

#### Beneficiary Location

```eval_rst
.. jsonschema-titles:: ../schema/360-giving-schema.json
    :child: beneficiaryLocation
```

#### Funding Org:Location

```eval_rst
.. jsonschema-titles:: ../schema/360-giving-schema.json
    :child: fundingOrganization/0/location
```

#### Recipient Org:Location

```eval_rst
.. jsonschema-titles:: ../schema/360-giving-schema.json
    :child: recipientOrganization/0/location
```

#### Related Document

```eval_rst
.. jsonschema-titles:: ../schema/360-giving-schema.json
    :child: relatedDocument
```

#### Classifications

```eval_rst
.. jsonschema-titles:: ../schema/360-giving-schema.json
    :child: classifications
```

#### Funding Type

```eval_rst
.. jsonschema-titles:: ../schema/360-giving-schema.json
    :child: fundingType
```

#### Grant Programme

```eval_rst
.. jsonschema-titles:: ../schema/360-giving-schema.json
    :child: grantProgramme
```

#### Transactions

The 360Giving Data Standard also allows for the reporting of three types of transactions:

* commitmentTransaction
* disbursementTransaction
* applicationTransaction

These do not currently have nice human readable titles, but can still be added as spreadsheet columns if needed.

To create the column titles, refer to the 360Giving JSON Schema and use the JSON pointer paths as column titles. e.g. commitmentTransaction/0/id

```eval_rst
.. _one-to-many-relationships:
```

### One to many relationships

Each of the sections of additional fields above can have multiple occurrences for one grant. There are three ways of describing this in a spreadsheet.

##### Additional sheets

Use the other sheets in the <a href="../_static/summary-table/360-giving-schema-titles.xlsx">360Giving Spreadsheet Template</a>. These have the columns described above, plus an extra column at the start for the Identifier of the relevant grant.

For the Funding Org: Location and Recipient Org: Location there is also an extra column for the Identifier of the relevant Funding/Recipient Org.

##### Numbering

You can describe multiple occurrences within the Grants sheet by having multiple columns. Use `:<num>:` instead of a `:`. This imitates JSON Pointer's approach.

e.g. to have two related documents with their own title and web address:

```eval_rst
+------------------------+------------------------------+------------------------+----------------------------------+
|Related Document:0:Title|Related Document:0:Web Address|Related Document:1:Title|Related Document:1:Web Address    |
+------------------------+------------------------------+------------------------+----------------------------------+
|A Document              |http://example.com/adocument  |Another Document        |http://example.com/anotherdocument|
+------------------------+------------------------------+------------------------+----------------------------------+
```

##### Multiple Rows

You can place the additional information about a grant in an additional row. Use the same Identifier for the grant, and place the additional information in the relevant columns. Consuming applications will then be able to try to merge the information into a single record, so be careful not to place contradictory information in fields that cannot have more than one value (e.g. a title or description)


### Field guidance

#### Dates and times

360Giving requires you to provide information on when a grant was awarded, and allows you to add details of when a project is taking place, and when you last updated information about aspects of the grant.

There are three different rules for validating dates:

##### Full dates (Award Dates and Transaction Dates)
The ```Award Date``` **must** provide a full date, including year, month and day in YYYY-MM-DD format (e.g. 2017-04-02 for the 2nd April 2017).

In some rare cases, an award date might also need to include the time of the grant, using a date-time format (e.g. 2017-04-02T16:45:00Z - a grant made at 4.45pm).

```eval_rst

.. hint::
  You can set Excel to present a date column in YYYY-MM-DD format using a custom format `as described here`_.

.. _as described here: http://superuser.com/questions/409896/how-do-i-enter-dates-in-iso-8601-date-format-yyyy-mm-dd-in-excel-and-have-exc/409899#409899

```

##### Uncertain dates (Planned Dates and Actual Dates)
Other events in the lifetime of a grant, such as for when the funded activity will take place, may include less specific date information. Funders should aim to be as specific as they can be, but do not need to guess at the particular day or month when an activity will take place if they are not certain or do not yet know.

Dates in the ```Planned Dates``` and ```Actual Dates``` groups should be provided in YYYY-MM-DD format, but the day or the day can be dropped or on the year provided (e.g. YYYY-MM or YYYY).

For example, if an application only indicates that a project will start in May 2019, then the ```Planned Dates:Start Date``` value may be '2019-05'.

It is up to users of the data to judge how to interpret dates which only include a year, or year and month. Different applications and analysis may require different judgements.

##### Date-time (Last Modified dates)
All rows in a 360Giving spreadsheet, and all objects in the JSON structure, can have a ```Last Modified``` date.

If used, this must always be in full date-time format so that if multiple updates take place on a single day, consuming applications can work out which version to use.

``` eval_rst

.. hint::
  You can set Excel to present a date column as a full date-time using the custom format of "yyyy-mm-ddThh:mm:ssZ". If you also set the formula for the entire column to ```=Now()``` then this value will be refreshed automatically every time you save the file.
```

### Conformance

In order to conform with the spreadsheet standard:

You must:

* **Read the column definitions carefully and follow the format they request** - for example, formatting identifiers and dates according to the standard. Full reference information is provided below.
* **Provide an Identifier** for each grant
* **Update the Last Modified date** whenever the status of a grant changes

You can:

* **Remove or hide non-required columns that you are not using** - although make sure you check for any [hidden columns](#hidden-columns) before publishing your data, and always remove rather than hide sensitive information.
* **Re-order the columns** so that information is arranged in the way you want
* **Add extra columns** to include information you want to share, but that is not covered by the standard. (See [additional fields](additional-fields)).
* **Move columns** in the <a href="../_static/summary-table/360-giving-schema-titles.xlsx">360Giving Spreadsheet Template</a> between sheets.

You must not:

* **Add extra rows at the top of the table**
* **Change the field names provided by the standard**

## CSV (.csv)

**TODO**
