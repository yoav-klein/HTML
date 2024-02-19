# Chapter 8 - Tables
---

Introduced:
`<table>` - this is the main element for the table.
`<tr>` - a table row.
`<td>` - table data, this is a single cell.
`<th>` - table header. In the first row we put headers to the columns.
Also, in each row we have a header to the row (Morning, Break, etc.)

Also, note the `colspan` and `rowspan` attributes that you can set on `<td>` elements. This allows
a cell to span across several rows or several columns.

## Adding semantics
We've added semantics to the table using the:
`<thead>` - the heading of the table. This encloses the first row with the table headers.
`<tbody>` - the body of the table. This encloses all the rows, beside that last one.
`<tfoot>` - This is primarily for tables that have a summary line, like a total sum or something.

We've also added semantics using the `scope` attribute given to table headers