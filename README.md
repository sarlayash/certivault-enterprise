# CertiVault Enterprise

Static certificate management front end designed for GitHub Pages plus a Google Apps Script / Google Sheets backend.

## Run locally

Open `index.html` using any static server. The site starts with a working `CERT001` demo record. Admin demo password: `admin123`.

## Connect Google Sheets

1. Create a Google Sheet, then open **Extensions → Apps Script**.
2. Copy `engine/Code.gs`, deploy it as a Web App with access set to **Anyone**.
3. Paste its deployment URL into `APP.apiUrl` in `assets/js/app.js`.

The included backend uses a `Certificates` sheet as the source of truth and supports verification plus bulk upload requests.

## CSV format

`Certificate ID,Learner Name,Program,Purpose,Issue Date,Template,Organization Name`

Purpose must be Certificate of Completion, Certificate of Excellence, or Certificate of Participation. Template is 1–5.

Use `sample-learners-upload.csv` as a ready-to-upload reference file.

## No-backend QR verification (GitHub Pages)

For QR scanning on any phone without Google Sheets, the live site reads the root `sample-learners-upload.csv` file as its shared certificate registry. Replace that file with your latest learner CSV and commit/push it to GitHub. Dashboard uploads are local browser previews only; a static GitHub Pages website cannot save a CSV uploaded in the dashboard back to GitHub automatically.
