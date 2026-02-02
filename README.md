# 🚀 Getting Started — JavaScript Pivot Table Component (Syncfusion EJ2)

[![License](https://img.shields.io/badge/license-SEE%20LICENSE%20IN%20license-blue.svg)](license)
[![Last Updated](https://img.shields.io/github/last-commit/SyncfusionExamples/getting-started-with-the-javascript-pivot-table-component.svg)](https://github.com/SyncfusionExamples/getting-started-with-the-javascript-pivot-table-component/commits)
[![Languages](https://img.shields.io/github/languages/top/SyncfusionExamples/getting-started-with-the-javascript-pivot-table-component.svg)](https://github.com/SyncfusionExamples/getting-started-with-the-javascript-pivot-table-component)

> Quick-start JavaScript demo showing how to integrate Syncfusion EJ2 `PivotView` (Pivot Table) using CDN or local scripts. Demonstrates `FieldList`, `GroupingBar`, and `CalculatedField` with sample data.

> **Demo (official):** https://ej2.syncfusion.com/javascript/demos/#/fluent2/pivot-table/overview.html

---

# 📚 Table of Contents

- [🔍 Overview](#-overview)
- [✨ Features](#-features)
- [🧭 Quick Start](#-quick-start)
- [🧩 Minimal Example](#-minimal-example)
- [🗂️ Project Structure](#-project-structure)
- [⚙️ Customization & Notes](#-customization--notes)
- [🧪 Development & Tests](#-development--tests)
- [🤝 Contributing](#-contributing)
- [📜 License & Support](#-license--support)

---

## 🔍 Overview

This repository is a minimal JavaScript quick-start that demonstrates how to embed Syncfusion EJ2 `PivotView` into a plain JavaScript/HTML page. It uses CDN-hosted EJ2 scripts and CSS for fast prototyping and shows how to enable `FieldList` and calculated values.

## ✨ Features

- Browser-first example using CDN (`ej2.min.js`) and local sample data.
- `PivotView` with `showFieldList` enabled and calculated fields support.
- Self-contained demo: open `index.html` in a browser to run.
- Lightweight example ideal for prototyping or learning the API.

## 🧭 Quick Start

Steps to run:

```bash
git clone https://github.com/SyncfusionExamples/getting-started-with-the-javascript-pivot-table-component.git
cd getting-started-with-the-javascript-pivot-table-component
# Open index.html in your browser (double-click or use a static server)
```

## 🧩 Minimal Example

HTML includes CDN CSS and script (example excerpts from `index.html`):

```html
<!-- material theme and pivotview CSS from CDN -->
<link href="https://cdn.syncfusion.com/ej2/20.3.56/ej2-pivotview/styles/material.css" rel="stylesheet">
<!-- EJ2 bundle (includes pivotview) -->
<script src="https://cdn.syncfusion.com/ej2/20.4.38/dist/ej2.min.js"></script>
<script src="es5-datasource.js"></script>
<div id="PivotTable"></div>
<script src="index.js"></script>
```

Core initialization (`index.js`):

```js
var pivotTableObj = new ej.pivotview.PivotView({
  dataSourceSettings: {
    columns: [{ name: 'Date', caption: 'Date' }, { name: 'Product' }],
    dataSource: pivotData,
    expandAll: false,
    enableSorting: true,
    filters: [],
    drilledMembers: [{ name: 'Country', items: ['France'] }],
    formatSettings: [{ name: 'Amount', format: 'C0' }],
    rows: [{ name: 'Country' }, { name: 'State' }],
    values: [{ name: 'Amount', caption: 'Sold Amount' }, { name: 'Quantity', caption: 'Quantity' }]
  },
  height: 350,
  showFieldList: true
});
pivotTableObj.appendTo('#PivotTable');
```

Sample data (`es5-datasource.js`):

```js
var pivotData = [
  { Amount: 2100, Country: "Canada", Date: "FY 2005", Product: "Bike", Quantity: 22, State: "Alberta" },
  { Amount: 1100, Country: "Canada", Date: "FY 2006", Product: "Van", Quantity: 32, State: "Quebec" },
  { Amount: 3100, Country: "Canada", Date: "FY 2007", Product: "Car", Quantity: 22, State: "Alberta" },
  /* ...more rows (see es5-datasource.js) ... */
];
```

## 🗂️ Project Structure

- `index.html` — demo host with CDN links and CSS
- `index.js` — PivotView initialization (plain JavaScript)
- `es5-datasource.js` — sample dataset used by demo
- `README.md` — this file

## ⚙️ Customization & Notes

- Change CDN version numbers in `index.html` to match your installed EJ2 version.
- For production use, prefer installing specific packages (e.g., `@syncfusion/ej2-pivotview`) and bundling with Webpack/Rollup.
- For large datasets use virtualization and server-side aggregation.

## 🧪 Development & Tests

This repository is a static demo. To develop or test changes:

- Open `index.html` in a browser or run a local HTTP server (see Quick Start).
- For automated testing or packaging, add a build toolchain (Webpack) and test runner (Jasmine/Mocha) as needed.

## 🤝 Contributing

Contributions are welcome. Please fork the repository and open a pull request with a clear description of your change. Suggested guidelines:

1. Create a branch: `feature/<short-desc>`
2. Keep examples small and focused (this is a demo repo)
3. Update README or add sample files when adding features

Consider adding `CONTRIBUTING.md` and small issue/PR templates to help contributors.

## 📜 License & Support

Essential JS 2 library is available under the Syncfusion Essential Studio program,  and can be licensed either under the Syncfusion Community License Program or the Syncfusion commercial license.

To be qualified for the Syncfusion Community License Program you must have a gross revenue of less than one (1) million U.S. dollars ($1,000,000.00 USD) per year and have less than five (5) developers in your organization, and agree to be bound by Syncfusion’s terms and conditions. 

Customers who do not qualify for the community license can contact sales@syncfusion.com for commercial licensing options.

Under no circumstances can you use this product without (1) either a Community License or a commercial license and (2) without agreeing and abiding by Syncfusion’s license containing all terms and conditions. 

The Syncfusion license that contains the terms and conditions can be found at 
https://www.syncfusion.com/content/downloads/syncfusion_license.pdf
