# README Documentation Best Practices – Custom Instructions for AzureSynapseEndToEndDemo

When creating or updating any README.md file in this repository, follow these best practices to ensure clarity, completeness, and professionalism. This repository provides one-click infrastructure and artifact deployment for Azure Synapse Analytics to get you started with Big Data Analytics on a large sized Health Care sample data.

---

## 📌 Project Context

- **Domain:** Azure Synapse Analytics, Big Data, Health Care Data
- **Purpose:** One-click infrastructure and artifact deployment for Azure Synapse Analytics using large-sized Health Care sample data (generated via [Synthea](https://synthea.mitre.org/)).
- **Key Technologies:** Azure Synapse Analytics, ARM Templates, Dedicated SQL Pool, Spark Pool, ADLS (Azure Data Lake Storage), FHIR, PySpark, T-SQL
- **Audience:** Data engineers, data analysts, and cloud architects looking to learn how to ingest, process, and serve large volumes of data using various components of Synapse.
- **License:** MIT

## 📂 Repository Structure

This repository is organized as a series of exercises with supporting resources:

```
├── ARMTemplate/             # Azure Resource Manager deployment templates
├── Exercise00-Setup/        # Initial setup and deployment instructions
├── Exercise01-Claims/       # Claims data pipeline exercise
├── Exercise02-Observations/ # Observations data pipeline exercise
├── Exercise03-Patients/     # Patients data pipeline exercise
├── Images/                  # Screenshots, GIFs, and diagrams
├── Troubleshooting/         # Common issues and solutions
├── artifacts/               # Synapse workspace artifacts
├── mybigdata/               # Big data assets
├── README.md                # Root README (project overview)
├── LICENSE                  # MIT License
└── SECURITY.md              # Security policy
```

---

## 📐 Structure & Required Sections

### For the Root README (`README.md`)

The root README should include the following sections (in order):

1. **Project Title & Badges**
   - A clear, descriptive project name as an H1 heading.
   - Badges for build/deployment status, license, and Azure compatibility.
   ```md
   # Azure Synapse End-to-End Demo
   ![License](https://img.shields.io/github/license/chikamsoachumsft/AzureSynapseEndToEndDemo)
   ```

2. **Short Description**
   - 1–2 sentences summarizing what the project does and why it exists.
   - Always answer: *What problem does this solve?*

3. **Reference Architecture**
   - Include the architecture diagram with descriptive alt text.

4. **Features / Highlights**
   - Bullet list of key capabilities (e.g., one-click deployment, health care sample data, Spark notebooks, Dedicated SQL Pool integration).

5. **Prerequisites**
   - Clearly list all requirements (GitHub account, Azure subscription, required permissions).

6. **Quick Start / Getting Started**
   - Link to Exercise 00 - Setup with a brief description of what the user will do.
   - Include the "Deploy to Azure" button prominently.

7. **Exercises / Table of Contents**
   - Numbered or bulleted list of all exercises with brief descriptions.
   - Use relative links to each exercise's README.

8. **Configuration / Parameters**
   - Document key parameters users will need (StorageName, DatabaseName, ServerName, SparkPoolName, DatasetSize).
   - Use a table format:
     | Parameter       | Description                                      | Example       |
     |-----------------|--------------------------------------------------|---------------|
     | `StorageName`   | Name of your Synapse workspace ADLS account      | `mystorage`   |
     | `DatabaseName`  | Name of your Dedicated SQL Pool database         | `mydb`        |
     | `DatasetSize`   | Size of the dataset to use                       | `1tb` / `30tb`|

9. **Troubleshooting**
   - Link to the Troubleshooting folder.

10. **Contributing**
    - How to file issues, submit PRs, and any code style expectations.

11. **License**
    - State the MIT license and link to the LICENSE file.

---

### For Exercise READMEs (`ExerciseXX-*/README.md`)

Each exercise README should follow this structure:

1. **Objective** — Clear description of what the exercise accomplishes.
2. **Prerequisites** — What the user needs before starting (e.g., "Complete Exercise 00 - Setup").
3. **Architecture / Pipeline Diagram** — Visual of the pipeline being built with descriptive alt text.
4. **Step-by-Step Instructions** — Numbered steps with:
   - Screenshots for every portal/UI action.
   - Code blocks for any commands or scripts.
   - Callout boxes for important notes and warnings.
5. **Parameters** — Table of parameters the user needs to configure.
6. **Validation** — How the user can verify the exercise completed successfully.
7. **Navigation** — Link to the next exercise at the bottom.

---

## ✍️ Writing Style

- **Be concise.** Respect the reader's time. Avoid unnecessary jargon.
- **Use active voice.** "Click the Debug button" not "The Debug button should be clicked."
- **Write for newcomers.** Assume the reader is seeing Azure Synapse for the first time.
- **Use consistent formatting.** Stick to one heading style, one list style, etc.
- **Use second person.** Address the reader as "you."
- **Be encouraging.** Use congratulatory messages at exercise completion (e.g., "Congratulations on completing Exercise 01!").

---

## 🧰 Formatting Rules

- Use **fenced code blocks** with language identifiers for all code:
  - Use `sql` for T-SQL scripts.
  - Use `python` for PySpark / Python code.
  - Use `json` for ARM templates and FHIR data.
  - Use `bash` for CLI commands.
- Use **tables** for structured data (parameters, configuration options, etc.).
- Use **blockquotes with emoji** for important callouts:
  ```md
  > :exclamation: **Important:** Write down all parameter values during deployment.
  ```
  ```md
  > *Note: Make sure your Dedicated Pool is running before executing this pipeline.*
  ```
- Use **relative links** for files within the repo (e.g., `./Exercise01-Claims/README.md`).
- Use **descriptive link text** — avoid "click here."
- Place **images from the `/Images` directory** using relative paths.

---

## ♿ Accessibility

- Add **descriptive alt text** to all images: `![Architecture diagram showing data flow from ADLS to Synapse](url)`. 
- Do not use generic alt text like `![image](url)` — describe what the screenshot shows.
- Use **semantic heading hierarchy** (don't skip levels: H1 → H2 → H3).
- Don't rely solely on images to convey critical information — always include text descriptions.

---

## 🔗 Azure-Specific Guidelines

- Always use the **"Deploy to Azure" badge** for one-click deployment links.
- When referencing Azure portal navigation, use **bold** for UI elements (e.g., **Review + Create**, **Manage Hub**, **SQL Pools tab**).
- When documenting ARM template parameters, include the parameter name, description, and any constraints.
- Always mention if a resource needs to be **running** before an operation (e.g., Dedicated SQL Pool).
- Include links to official Microsoft documentation where relevant.

---

## 🚫 Common Mistakes to Avoid

- ❌ Generic alt text on images (e.g., `![image](url)`).
- ❌ Missing prerequisites for exercises.
- ❌ Outdated screenshots that don't match the current Azure portal UI.
- ❌ Hardcoding user-specific values (storage account names, resource group names).
- ❌ Forgetting to mention the license.
- ❌ Broken relative links between exercises.
- ❌ Missing navigation links to the next/previous exercise.
- ❌ Walls of text without screenshots for portal-based steps.

---

## 🔄 Maintenance

- **Review all READMEs** when Azure Synapse portal UI changes.
- **Test all "Deploy to Azure" links** periodically.
- **Verify all screenshots** match the current portal experience.
- **Check relative links** between exercises for 404s.
- **Update parameter documentation** if new parameters are added.

---

## ✅ README Quality Checklist

Before finalizing any README, confirm:

- [ ] Can a new user understand the exercise objective within 30 seconds?
- [ ] Are all prerequisites listed?
- [ ] Are all parameter values documented in a table?
- [ ] Do all images have descriptive alt text?
- [ ] Are all code blocks syntax-highlighted with the correct language?
- [ ] Are all relative links valid?
- [ ] Is there a "Deploy to Azure" button where applicable?
- [ ] Is there a navigation link to the next exercise?
- [ ] Are important notes and warnings clearly called out?
- [ ] Is the license stated in the root README?