# Postman API Testing Task

**Repository:** [Postman-newman-ghActions](https://github.com/WannaBeDream/Postman-newman-ghActions)

## Requirements:
1. **Post on Git:** Push the collection and environment files to the repository.
2. **Pipeline Launch:** Set up a GitHub Actions pipeline to run tests using Newman.
3. **GitHub Pages:** Automatically push the Newman test results (HTML reports) to GitHub Pages.

## Step-by-Step Instructions:

### Phase 1: Preparation (Local)
1. **Export Postman Collection:**
   - In Postman, export your Collection as a JSON file (v2.1).
   - Export your Environment (if any) as a JSON file.
2. **Move files to Repository:**
   - Place the exported JSON files into your local repository folder: `d:\other\TestSquadLLC\git-repos\Postman-newman-ghActions`.
3. **Initialize NPM:**
   - Run `npm init -y` to create a `package.json`.
   - Install Newman and the HTML reporter: `npm install newman newman-reporter-htmlextra --save-dev`.

### Phase 2: GitHub Actions Workflow
1. **Create Workflow File:**
   - Create a directory `.github/workflows`.
   - Create a file named `main.yml` inside it.
2. **Define the Workflow:**
   - Set up the environment (Node.js).
   - Install dependencies (`npm install`).
   - Run Newman tests and generate the report.
   - Use a deployment action (like `peaceiris/actions-gh-pages`) to push the report to the `gh-pages` branch.

### Phase 3: GitHub Pages Configuration
1. **Push Changes:**
   - `git add .`
   - `git commit -m "Add Postman tests and workflow"`
   - `git push origin main`
2. **Enable GitHub Pages:**
   - Go to your repo Settings -> Pages.
   - Set the source to the `gh-pages` branch.
