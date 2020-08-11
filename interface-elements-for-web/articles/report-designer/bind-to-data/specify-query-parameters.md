---
title: Specify Query Parameters
author: Anna Vekhina
---
# Specify Query Parameters

Each query in an [SQL data source](bind-a-report-to-a-database.md) contains a collection of query parameters. A query parameter holds an external value that is inserted into an SQL statement before the query is executed. This value can be either static, if specified explicitly, or dynamic, when an [expression](../use-expressions.md) is evaluated to obtain a value.

The query parameter value is inserted into the SQL query at the "\@QueryParameterName" placeholder's position.

Use query parameters to:

* **Filter report data at the data source level**

	The [Query Builder](../report-designer-tools/query-builder.md) helps you construct SQL queries when creating a new data-bound report or [binding a report to an SQL data source](bind-a-report-to-a-database.md).

	![](../../../images/eurd-web-query-parameters-create-query.png)

	You can also add or edit queries in an SQL data source.

	![](../../../images/eurd-web-query-parameters-add-edit-queries.png)

	Expand the **Parameters** section in the **Query Builder** to add a new query parameter.

	![](../../../images/eurd-web-query-parameters-add-in-query-builder.png)

	Expand the **Query Properties** section and click the **Filter** property's ellipsis button to invoke the Filter Editor where you can specify filter conditions that include the created query parameters.

	![](../../../images/eurd-web-query-parameters-in-filter-editor.png)

	The specified filter conditions are added as an SQL statement's WHERE part.

* **Specify parameters for a stored procedure**

	The Data Source Wizard includes the following page.

    ![](../../../images/eurd-web-query-parameters-select-stored-procedure.png)

    If you select a stored procedure, the wizard creates a query parameter for each procedure parameter and allows you to configure the created query parameters in the next **Configure query parameters** page.

	![](../../../images/eurd-web-query-parameters-for-stored-procedure.png)

## Configure Query Parameters

The following properties are available for a query parameter:

* **Name** - the parameter name.
* **Type** - the parameter value's data type.
* **Expression** - determines whether the parameter value is static or dynamic.
* **Value** - the parameter value. If the **Expression** option is enabled, this property contains an expression that is parsed and processed to obtain the parameter value. An expression can include data source fields or [report parameters](../shape-report-data/use-report-parameters.md).

## Specify the Query Parameter Value

Below, you can see how a value is specified for a query parameter within the Data Source Wizard's page. You can also specify query parameter values in the Report Wizard or the Query Parameters dialog in the same way.

* **Specify a static value**

	Choose a query parameter's value type and set a static value to the **Value** property according to the selected type.

	![](../../../images/eurd-web-query-parameters-static-value.png)

* **Set a dynamic value**

	Expand the **Type** property's drop-down list and select **Expression**.

	![](../../../images/eurd-web-query-parameters-dynamic-expression.png)

	Click the **Value** property's ellipsis button and construct an expression in the invoked [Expression Editor](../report-designer-tools/expression-editor.md). You can map a report parameter that already exists in a report to a query parameter.

	![](../../../images/eurd-web-query-parameters-expression-editor.png)

## Pass a Multi-Value Parameter Value to a Query

You can map [multi-value parameters](../shape-report-data/use-report-parameters/multi-value-report-parameters.md) to query parameters. For instance, the following query selects the orders whose IDs are listed in the _\@OrderID_ query parameter.

![](../../../images/eurd-web-query-parameters-map-to-multi-value-parameter.png)

## Pass a Multi-Value Report Parameter Value to a Stored Procedure

You cannot pass a [multi-value parameter](../shape-report-data/use-report-parameters/multi-value-report-parameters.md) value to a stored procedure directly. Use one of the following expression functions:

* Use the [Join() expression function](../use-expressions/expression-syntax.md) to convert the array of parameter values to a string if you use MS SQL Server, MySQL or Oracle database systems.

	![](../../../images/eurd-web-query-parameters-join-expression-function.png)

* Use the [CreateTable() expression function](../use-expressions/expression-syntax.md) to prepare a table using values of several multi-value parameters.

	![](../../../images/eurd-web-query-parameters-createtable-expression-function.png)