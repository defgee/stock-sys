# TapTrack — Bar Operations Demo

A lightweight, mobile-first demonstration app for bar sales and stock control. It uses plain HTML, CSS and JavaScript, a JSON seed file, and browser `localStorage` for demo changes. No backend or API keys are required.

## Run locally

Because the app loads `data.json`, serve the folder over HTTP rather than opening `index.html` directly. For example:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000` on your computer. To test on your phone on the same Wi-Fi, use your computer's local IP address, e.g. `http://192.168.1.10:8000`.

## Deploy to Vercel

1. Create a GitHub repository and upload the contents of this folder.
2. In Vercel, choose **Add New → Project** and import the repository.
3. Framework preset: **Other**. Build command: leave blank. Output directory: `.`.
4. Deploy. The site is static; no environment variables are needed.

You can also deploy the folder using Vercel CLI with `vercel --prod` from this directory.

## Demo features

- Bartender selector; each sale records the selected staff member.
- Sales recording with product, quantity, payment method and timestamp.
- Simulated barcode lookup using the sample barcode values.
- Stock automatically decreases when a sale is recorded.
- Stock receipts, breakages, complimentary drinks and manual adjustments.
- Opening and closing physical counts with variance calculation.
- Overview and reports for recorded sales, staff totals, low stock and count variances.
- Changes persist in the same browser using `localStorage`.

## Important limitations

This is a sales demo, not a production inventory system. Data is stored only in the current browser on the current device. It does not sync between phones, provide secure authentication, or protect against users editing browser data. The JSON file is the initial sample dataset; after first load, the browser's saved copy is used. Reset demo data from the Reports page.

For a real deployment with multiple bartenders/devices, replace `localStorage` with a backend API and database (for example Flask + PostgreSQL). A JSON file on a static Vercel deployment is not a safe writable shared database.
