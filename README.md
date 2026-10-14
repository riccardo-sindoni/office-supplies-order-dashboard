# Office Supplies Order Dashboard

**Live demo:** https://riccardo-sindoni.github.io/office-supplies-order-dashboard/

I built a single-file web dashboard (HTML + JavaScript, no backend) to monitor office and consumable supply orders across a network of retail stores, starting from the supplier's order-confirmation PDFs.

> **Demo version:** store names, orders, prices and addresses are all **fictitious**. The demo opens with sample data so every feature can be explored.

> **Language note:** the interface is in Italian because the tool is built around Italian order confirmations (Lyreco format), Italian number and date formats and 22% VAT.

## Business problem
In a multi-store retail business, each store orders office, cleaning and printing supplies from the same supplier. The confirmations arrive as individual PDFs, so nobody has a consolidated view: it is hard to tell which store has not ordered for months, how spend splits across categories, or whether unit prices drift from one order to the next. I wanted a simple tool that answers those questions without a database or any IT project.

## What the dashboard does
- Traffic-light status per store, based on days since the last order (configurable thresholds)
- Group KPIs: total orders, total spend, average order value, stores without recent orders
- Store detail view: monthly spend, spend by category, products purchased with price change since the first purchase, estimated next order date, full order history
- Automatic product categorisation by keywords (cleaning, paper and hygiene, stationery, toner and printing), editable in the settings
- PDF order-confirmation import with text extraction in the browser, followed by a review screen before saving
- JSON backup export/import and CSV export

## Design decisions
- **Manual store assignment:** the store is chosen for every imported file instead of being guessed from the delivery address, which avoids attributing an order to the wrong store.
- **Validation before saving:** the tool checks that line totals add up to the order total, flags missing fields and blocks duplicate order numbers.
- **Net, VAT and gross:** the PDF reports only the net amount per line, so VAT and gross are derived using the order's VAT rate and marked as calculated values.
- **Privacy by design:** PDFs are read locally and data stays in the browser's localStorage; nothing is sent to any server.

## How I built it
I defined the business problem, the data to extract, the status rules and the validation checks. I built the dashboard with the help of an AI assistant (Claude, by Anthropic), which wrote the HTML and JavaScript from my specifications. My role was to specify what the tool had to do, review the output, test it with order confirmations and check that the totals reconciled. I then anonymised the project and added the sample data you see in the demo.

## Usage
Open `index.html` in a browser, or use the live demo. On first launch the demo data is loaded. **Svuota archivio** starts from scratch and **Carica dati demo** restores the sample data. To use it with your own stores, edit the `PV_LIST` array in `index.html`.

## Tools
HTML, CSS, vanilla JavaScript, PDF.js (loaded from cdnjs), localStorage, hand-drawn SVG charts.

## What I learned
Working with real-world documents means designing for messy input: a parser alone is not enough, it needs validation, a review step and an easy way to correct data by hand.
