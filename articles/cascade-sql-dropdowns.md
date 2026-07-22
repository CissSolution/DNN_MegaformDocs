# Cascade-SQL Dropdowns (DNN)

Build dependent dropdowns whose options come from a SQL table, where selecting a
value in the **parent** dropdown filters the **child** dropdown — for example
Country → State → City.

> **Status:** this guide is being finalized with a real, verified build on a live
> DNN 10.3 form (against a demo table on the QA database) and a slow animation.
> The mechanics below are accurate.

## How it works

A dropdown reads its options from SQL when the field is configured with:

- `optionsSource: "sql"`
- `optionsConnectionKey` — the named connection to read from (site DB or a
  registered connection)
- `optionsSql` — a `SELECT value, label FROM …` query

The **child** dropdown adds a parameter bound to the parent's selected value. On
DNN the parent value is passed as a query-string parameter (prefixed so the
server binds it as a named SQL parameter), and the child re-queries whenever the
parent changes.

## ⭐ Gotchas to avoid

- A SQL dropdown returns an **empty list silently** if `optionsConnectionKey` or
  `optionsSource: "sql"` is missing. Always set both.
- Anonymous/public forms hit the **strictest bounded-read cap**, so pair a large
  option set with a client typeahead (`&q=` / `&page=`) — otherwise rows are
  dropped silently.
- The connection is server-gated against the admin allow-list; a key the operator
  never registered can never be queried.

## Prerequisites

- DNN 10.x, MegaForm installed, Host/Administrator access.
- A demo table with a parent→child relationship (e.g. Country/State/City).

*Full verified build (parent SQL → child parent-filter → live change) + animation coming shortly.*
