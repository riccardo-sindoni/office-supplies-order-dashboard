# Office Supplies Order Dashboard

**[Live demo](https://riccardo-sindoni.github.io/office-supplies-order-dashboard/)**

A single-file web dashboard (HTML + JavaScript, no backend) to monitor office and consumable supply orders across retail stores, starting from supplier order-confirmation PDFs.

> **Demo version:** store names, orders, prices and addresses are all **fictitious**.

> **Language note:** the interface is in Italian, because it is built around Italian order-confirmation PDFs (Lyreco format), Italian number and date formats, and 22% VAT.

## Features
- Traffic-light status per store, based on days since the last order (configurable thresholds)
- Store detail view: monthly spend, spend by category, products purchased, order history
- PDF order-confirmation import (text extraction with PDF.js, entirely in the browser)
- JSON backup export/import and CSV export

## Usage
Open `index.html` in a browser (or publish it with GitHub Pages). On first launch, demo data is loaded. Use **Svuota archivio** to start from scratch and **Carica dati demo** to restore the demo data.

Data is stored in the browser's `localStorage`: nothing is sent to any server. The only external dependency is PDF.js, loaded from cdnjs.

## Customization
Edit the `PV_LIST` array in `index.html` with your own stores.
