# Postman API Automation Integration with Github Actions #
This repository is a demonstration for POC for integrating postman tests with github actions. The tests are written in Postman and they are executed on the VM with the help of newman and newman-reporter-htmlextra.
Github Actions will trigger the project execution on every push to the main branch. You can also execute the project manually using workflow_dispatch. The projects runs on a scheduled time with the help of Cron Job.

The html report is archieved and kept in the artifact section for the team to download it. Along with that they can view the report directly from the github page : https://vvaidya6.github.io/Inwarranty-Flow-Collection/.
The latest report is mailed to the team members using GMAIL SMTP.

## Testing Coverage ## 
  1. Happy Flow Testing
  2. Negative Testing and Edge Case Testing
  3. Token Testing
  4. Data Driven Testing with CSV
  5. Schema Validation
  6. Secrets Management with Github Secrets

 

## Tech Stack ##
1. Postman
2. Node JS 24.4.1
3. Newman
4. Newman-Reporter-Htmlextra
5. Github Actions
6. Gmail SMTP
7. Github Pages
8. CSV for Data Driven Testing
9. AWS-EC2 instance for Self hosted github runner.



## Github Pages ##
You can directly view the latest test report of the Postman Test  at the Github Page Link: https://github.com/vvaidya6/Inwarranty-Flow-Collection

## HTML Report ##  
 The report will be created in newman folder
 
 ![Postman Report](https://github.com/vvaidya6/Inwarranty-Flow-Collection/blob/static-content/newman-report.png)

## Project Structure ## 
```
Phoenix Inwarranty Flow
├─ Inwarranty-flow Collection.postman_collection.json  #Collection File
├─ QA.postman_environment.json  #Environment File 
└─ testdata.csv  #testdata file

```

## How to run the project?  ##
You can run the project on your local system for that: 
1. Clone the project on Local System: https://github.com/vvaidya6/Inwarranty-Flow-Collection.git
2. Install Node JS and NPM from https://nodejs.org/en
3. Install Newman using ``` npm install -g newman ```
4. Install Newman-html-extra using ``` npm install -g newman-reporter-htmlextra ```
5. Run the Newman command:
   
   ```
              newman run 'Inwarranty-flow Collection.postman_collection.json' \  
             -e QA.postman_environment.json \
             -d testdata.csv \
             -r cli,htmlextra \
             --reporter-htmlextra-export ./newman/index.html
   ```
