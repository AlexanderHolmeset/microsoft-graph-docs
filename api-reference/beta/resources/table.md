---
title: "Table resource type"
description: "Represents an Excel table."
author: "lumine2008"
localization_priority: Normal
---

# Table resource type

> **Important:** APIs under the /beta version in Microsoft Graph are in preview and are subject to change. Use of these APIs in production applications is not supported.

Represents an Excel table.

## Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[Get Table](../api/table-get.md) | [Table](table.md) |Read properties and relationships of table object.|
|[Create TableColumn](../api/table-post-columns.md) |[TableColumn](tablecolumn.md)| Create a new TableColumn by posting to the columns collection.|
|[List columns](../api/table-list-columns.md) |[TableColumn](tablecolumn.md) collection| Get a TableColumn object collection.|
|[Create TableRow](../api/table-post-rows.md) |[TableRow](tablerow.md)| Create a new TableRow by posting to the rows collection.|
|[List rows](../api/table-list-rows.md) |[TableRow](tablerow.md) collection| Get a TableRow object collection.|
|[Update](../api/table-update.md) | [Table](table.md)	|Update Table object. |
|[Databodyrange](../api/table-databodyrange.md)|[Range](range.md)|Gets the range object associated with the data body of the table.|
|[Headerrowrange](../api/table-headerrowrange.md)|[Range](range.md)|Gets the range object associated with header row of the table.|
|[Range](../api/table-range.md)|[Range](range.md)|Gets the range object associated with the entire table.|
|[Totalrowrange](../api/table-totalrowrange.md)|[Range](range.md)|Gets the range object associated with totals row of the table.|
|[Clearfilters](../api/table-clearfilters.md)|None|Clears all the filters currently applied on the table.|
|[Converttorange](../api/table-converttorange.md)|[Range](range.md)|Converts the table into a normal range of cells. All data is preserved.|
|[Delete](../api/table-delete.md)|None|Deletes the table.|
|[Reapplyfilters](../api/table-reapplyfilters.md)|None|Reapplies all the filters currently on the table.|
|[List](../api/table-list.md) | [Table](table.md) collection |Get table object collection. |
|[Add](../api/tablecollection-add.md)|[Table](table.md)|Create a new table. The range source address determines the worksheet under which the table will be added. If the table cannot be added (e.g., because the address is invalid, or the table would overlap with another table), an error will be thrown.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|string|Returns a value that uniquely identifies the table in a given workbook. The value of the identifier remains the same even when the table is renamed. This property should be interpreted as an opaque string value and should not be parsed to any other type. Read-only.|
|name|string|Name of the table.|
|showHeaders|boolean|Indicates whether the header row is visible or not. This value can be set to show or remove the header row.|
|showTotals|boolean|Indicates whether the total row is visible or not. This value can be set to show or remove the total row.|
|style|string|Constant value that represents the Table style. Possible values are: TableStyleLight1 thru TableStyleLight21, TableStyleMedium1 thru TableStyleMedium28, TableStyleStyleDark1 thru TableStyleStyleDark11. A custom user-defined style present in the workbook can also be specified.|
|highlightFirstColumn|Boolean|Indicates whether the first column contains special formatting.	|
|highlightLastColumn|Boolean|Indicates whether the last column contains special formatting.	|
|showBandedColumns|Boolean|Indicates whether the columns show banded formatting in which odd columns are highlighted differently from even ones to make reading the table easier.	|
|showBandedRows|Boolean|Indicates whether the rows show banded formatting in which odd rows are highlighted differently from even ones to make reading the table easier.	|
|showFilterButton|Boolean|Indicates whether the filter buttons are visible at the top of each column header. Setting this is only allowed if the table contains a header row.	|
|legacyId|String|Legacy Id used in older Excle clients. The value of the identifier remains the same even when the table is renamed. This property should be interpreted as an opaque string value and should not be parsed to any other type. Read-only.	|

## Relationships
| Relationship | Type	|Description|
|:---------------|:--------|:----------|
|columns|[TableColumn](tablecolumn.md) collection|Represents a collection of all the columns in the table. Read-only.|
|rows|[TableRow](tablerow.md) collection|Represents a collection of all the rows in the table. Read-only.|
|sort|[TableSort](tablesort.md)|Represents the sorting for the table. Read-only.|
|worksheet|[Worksheet](worksheet.md)|The worksheet containing the current table. Read-only.|

## JSON representation

Here is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [
     "legacyId"
  ],
  "@odata.type": "microsoft.graph.table"
}-->

```json
{
  "highlightFirstColumn": true,
  "highlightLastColumn": true,
  "id": "String (identifier)",
  "name": "String",
  "showBandedColumns": true,
  "showBandedRows": true,
  "showFilterButton": true,
  "showHeaders": true,
  "showTotals": true,
  "style": "String",
  "legacyId": "String"
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Table resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
