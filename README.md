# 🛠️ In Warranty Flow Collection

This repository contains Postman collections and workflows for automating API testing related to the **In-Warranty Flow** process.  
It uses **Newman** (Postman CLI runner) integrated with **GitHub Actions** for automated scheduled runs and reporting.

---

## 📂 Repository Structure
.
├── In Warranty Flow Collection.postman_collection.json # Main Postman collection
├── QA.postman_environment.json # QA environment variables
├── testdata.csv # Test data for collection
├── .github/workflows/postman-tests.yml # GitHub Actions workflow
└── README.md # Project documentation

yaml
Copy
Edit

---

## 🚀 Features
- Automated API tests with Postman collections.  
- CI/CD integration with **GitHub Actions**.  
- Scheduled daily test runs (via cron).  
- Generates **Newman HTML reports** and uploads them as artifacts.  
- Supports running with external data files (`testdata.csv`).  

---

## ⚙️ How to Run Locally
1. Install [Node.js](https://nodejs.org) (v16+ recommended).
2. Install Newman:
   ```bash
   npm install -g newman newman-reporter-htmlextra
Run the collection:

bash
Copy
Edit
newman run "In Warranty Flow Collection.postman_collection.json" \
   -e QA.postman_environment.json \
   -d testdata.csv \
   -r cli,htmlextra
🔄 GitHub Actions Workflow
This repo uses a workflow file at .github/workflows/postman-tests.yml.

Runs automatically:

Every weekday at 11:30 AM IST

Daily at 8:00 AM IST and 7:30 PM IST

Generates Newman reports (.html + .json)

Uploads them as artifacts after each run.

📊 Reports
After every workflow run:

Go to the Actions tab → Select the latest run.

Download the Newman Report artifact (HTML report).

👥 Contributors
Vaibhav Vaidya (Repo owner & maintainer)

📌 Notes
If you face assertion limit issues, update Newman CLI options to include:

bash
Copy
Edit
--reporter-cli-no-truncate
--reporter-json-export newman/report.json
--reporter-htmlextra-export newman/report.html
✨ Happy Testing!
