# Display Submissions with Razor (DNN)

Read form-submission data with the MegaForm SDK and render it in your own Razor
views — as a **Card grid**, a **ListView / table**, or a **detail** layout — all
from the same submission data.

> **Status:** this guide is being finalized with **copy-paste-able Razor code**
> (verified against a live DNN site) and **screenshots of the rendered output**.
> The structure below shows what it will contain.

## What you'll build

Using the SDK reader from a DNN Razor host script (see
[DNN Razor Host](dnn-razor-host.md) and [Razor Host Examples](razor-host-examples.md)),
you query a form's submissions once and bind them to three different layouts:

1. **Card grid** — one card per submission, key fields highlighted.
2. **ListView / table** — columnar view for scanning many rows.
3. **Detail / stat tiles** — a single submission, or aggregate counters.

Each layout ships with its own `.cshtml` snippet you can paste into a DNN Razor
module.

## How reading works on DNN

DNN keeps the per-field `DataJson`, so the SDK reader returns each submission's
fields directly — see [Reading Data](reading-data.md) for the query surface
(filter by form, page, project columns).

## Prerequisites

- DNN 10.x, MegaForm installed, a form with a few submissions.
- The DNN Razor Host (or the SDK referenced from your own module).

*Full guide with real Razor code for each layout + rendered screenshots coming shortly.*
