# Postman-newman-ghActions
TestSquad Internship - API Automation Testing

## Overview
This repository contains an automated API testing setup using Postman, Newman, and GitHub Actions. The pipeline automatically runs tests on every push to the `main` branch and publishes a detailed HTML report using GitHub Pages.

## Project Structure
- `AQA-TS-lection13-TheDogsApi_v2.postman_collection.json`: The Postman collection containing the API tests for The Dogs API.
- `.github/workflows/main.yml`: GitHub Actions workflow configuration for the CI/CD pipeline.
- `package.json`: Node.js project configuration containing necessary dependencies (`newman` and `newman-reporter-htmlextra`).

## CI/CD Pipeline
The automated pipeline performs the following steps:
1. Checks out the code.
2. Sets up Node.js.
3. Installs dependencies (`newman` and `htmlextra` reporter).
4. Runs the Postman collection using Newman.
5. Generates an HTML report using the `htmlextra` reporter.
6. Deploys the generated report to GitHub Pages using `peaceiris/actions-gh-pages`.

## View Test Reports
The latest test reports are automatically published and can be viewed here:
👉 **[Newman Test Report](https://Lekuro.github.io/Postman-newman-ghActions/)**

## Local Execution
To run the tests locally on your machine, follow these steps:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Lekuro/Postman-newman-ghActions.git
   cd Postman-newman-ghActions
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Run the tests and generate a report:**
   ```bash
   mkdir -p reports
   npx newman run AQA-TS-lection13-TheDogsApi_v2.postman_collection.json -r htmlextra --reporter-htmlextra-export reports/index.html
   ```

4. **View the report:**
   Open the `reports/index.html` file in your web browser.

5. **run test locally:** 
   ```bash
   npx newman run AQA-TS-lection13-TheDogsApi_v2.postman_collection.json
   ```
