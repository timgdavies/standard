# Your guide to metadata
This page contains guidance on metadata in 360Giving. What it is, why it's important, and how you can add metadata to your new or existing 360Giving data.

## What is metadata and why should you publish it?
Metadata is data about data. If you've ever looked at the file size of a file on your computer you've used metadata. Metadata is useful to assist humans and computers to build a picture of what the contents of a dataset are so they can make decisions about how to use it.

In the context of the 360Giving standard metadata allows publishers of 360Giving data to declare information about their data in a way that can be easily read by humans and machines. Declaring metadata helps people such as data users understand what is contained in your data and if people understand what is in your data then they'll be able to determine whether or not it fits their needs. These needs will likely be based around criteria such as information about the grant e.g. the date range of grants in the file, whether beneficiary location is included etc. Further to this, publishers of 360Giving data may want to make sure that a data user understands some of the context around their data before they use it.

Both of these needs require information which is essentially metadata. We hope that by including metadata in the 360Giving standard ensures that we are better serving the needs of publishers and data users.

If you would like to read more about what metadata is and why it's useful some more information may be found in [this blog post](https://www.threesixtygiving.org/2019/03/20/metadata-explaining-the-data/).


## Metadata in the 360Giving Standard
The metadata in the 360Giving Standard is authoritative metadata that the publisher declares about *the file or dataset* (not the grant itself). In the schema, it sits in [package schema](../schema/package-schema) and is declared using the fields in the package schema (except for `grants` which is a list of grant data).

```eval_rst
.. jsonschema:: ../../schema/360-giving-package-schema.json
```

## How do I add metadata to my 360Giving data?

This will depend on how you are publishing your 360Giving data. If you are publishing using JSON then your API or server should populate the appropriate fields in [package schema](../schema/package-schema).

### Adding metadata to an Excel (.xlsx) format spreadsheet
You may add metadata to an Excel formatted spreadsheet by following these steps:

1. Add a tab to the spreadsheet called `Meta`.
2. In the first column (usually 'A') put the names of the metadata fields you wish to include. You can find the names by looking at the `Title` of the field on [package schema](../schema/package-schema) page.  For example for the `version` field you can write `title` or `title`. For some fields you may need to declare them as part of a larger object. For these use a colon in the name e.g. `Publisher:Name` for your publisher name and `Publisher:Website` for you website URL.
3. In the second column (usually 'B') you should fill out these with the appropriate values. Some fields require different types of values such as URLs or dates. You should check what these are by checking the [package schema information](../schema/package-schema).
4. You should check whether your file is valid by uploading it to the [Data Quality Tool](https://dataquality.threesixtygiving.org/). It will tell you if you need to make any changes to the metadata you've added before you publish the file.
5. Publish the file how you normally do.

Our updated <a href="../../_static/summary-table/360-giving-schema-titles.xlsx">360Giving Spreadsheet Template</a> contains a tab already made for metadata.

### Adding metadata to a CSV (.csv) format spreadsheet

> TODO finish this with details of the implementation once they're known and implemented in flatten-tool
