# JSON to Excel Converter

A lightweight, browser-based tool for loading JSON data, viewing it as a table, searching and sorting rows, and downloading the data as a CSV file that can be opened in Excel.

> **Note:** The current download implementation creates `data.csv`; it does not generate a native `.xlsx` workbook.

## Features

- Paste JSON into the text area or upload a `.json` file.
- Display an array of JSON objects as a table.
- Search values across the loaded rows.
- Sort by clicking a column heading.
- Browse results in pages of 10 rows.
- Download the loaded data as `data.csv`.

The parser also accepts a JSON object with a `data` array, for example `{ "data": [{ "name": "Example" }] }`.

## Getting started

1. Download and extract [`json-to-excel-app.zip`](json-to-excel-app.zip).
2. Open the extracted `index.html` in a modern browser.
3. Paste JSON or choose a `.json` file, then load the data.
4. Search, sort, or page through the table, and choose **Download Excel** to save a CSV file.

No package installation or build step is required; the app runs locally in the browser.

## Expected JSON format

The table expects a non-empty array of objects with consistent fields:

```json
[
  { "name": "Alice", "age": 30 },
  { "name": "Bob", "age": 25 }
]
```

Alternatively, wrap the array in a `data` property:

```json
{
  "data": [
    { "name": "Alice", "age": 30 },
    { "name": "Bob", "age": 25 }
  ]
}
```

## Branches

| Branch | Purpose / contents |
| --- | --- |
| `main` | Default branch. Contains the project files and the `json-to-excel-app.zip` bundle. |
| `Sameer-Programmer-patch-1` | Patch/upload branch, merged into `main`. Contains the same project file set and app logic as `main`. |

The two branches currently share the same application files; `main` is the default branch to use for the latest repository state.

## Repository files

- `script.js` — JSON loading, table rendering, search, sorting, pagination, and CSV download logic.
- `style.css` — basic page and table styling.
- `json-to-excel-app.zip` — downloadable bundle containing the HTML, CSS, and JavaScript app files.
- `index.html` — root-level HTML file.

## Current limitations

- Export is CSV, not `.xlsx`.
- Input should be a non-empty array of objects (or an object containing such an array under `data`).
- The repository's root-level `index.html` is currently empty. Use the HTML bundled in `json-to-excel-app.zip` to launch the app.
