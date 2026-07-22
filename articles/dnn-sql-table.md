# Read & Write a SQL Table Directly (DNN)

MegaForm can point at an existing SQL Server table in your DNN database (or a
named connection) and turn it into a form: browse the table, drop its columns
onto the canvas as fields, and have submissions written straight back into the
table.

> **Status:** this guide is being finalized with a step-by-step, verified
> walkthrough and a slow animation recorded on a live DNN 10.3 site. The outline
> below reflects the real flow.

## What you'll do

1. Open a form in the **Builder** and switch to the **DB** tab.
2. **Pick the connection** — the site database (`DashboardDatabase`) or any
   admin-registered named connection (see [Cascade-SQL Dropdowns](cascade-sql-dropdowns.md)
   and Database Settings for how connections are registered).
3. **Choose a table** — the DB tab lists the base tables on the selected
   connection. Click **⚡ Capability** to see what MegaForm can do with it
   (key, required columns, permissions).
4. **Build the form** — use **+ DataGrid** to insert a self-configured subform,
   or drag individual **column chips** onto the canvas as input fields (identity
   primary keys are skipped automatically).
5. **Submit** — a submission writes a row back into the SQL table through the
   server-resolved connection.

## Notes & safety

- The connection you pick is **never trusted from the browser**: the server
  re-checks it against an admin allow-list before reading or writing, so a table
  can only be reached on a connection the operator registered.
- Column → field matching is by name similarity; review the generated fields
  before publishing.

## Prerequisites

- DNN 10.x with the MegaForm module installed, Host/Administrator access.
- A target table on the site database or a registered named connection.

*Full verified walkthrough + animation coming shortly.*
