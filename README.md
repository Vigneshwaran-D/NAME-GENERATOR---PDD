# Create a detailed README.md file with more explanation, visuals, and section headers

detailed_readme = """
# 💼 UiPath RPA Project: Name Generator Automation

This UiPath project automates the process of generating fake identities from [FakeNameGenerator.com](https://www.fakenamegenerator.com/) using gender preferences and configuration settings provided in a CSV input file.

It extracts key details, stores results in a CSV, and produces summary `.txt` files for the oldest and youngest generated persons.

---

## 📌 Use Case Overview

- 🤖 Automate the manual effort of generating fake names for testing or simulation purposes.
- 📤 Input via CSV: Define how many Male and Female records are needed.
- 🧠 Uses UI automation to navigate and extract data from the FNG website.
- 🗃️ Outputs sorted data to CSV and individual TXT files for recordkeeping.

---

## 🛠 Project Structure


NameGeneratorProject/ ├── Main.xaml # Main entry workflow ├── InitAllSettings.xaml # Reads config and prepares folders ├── LoadInputData.xaml # Loads and validates input.csv ├── ProcessTransaction.xaml # Calls FNG website and extracts data ├── GenerateTextFiles.xaml # Creates .txt summaries ├── ExceptionHandler.xaml # Handles any errors/exceptions ├── project.json # Project metadata for UiPath ├── Settings/ │ └── Config.xlsx # Key-value config entries ├── Input/ │ └── input.csv # User-specified gender & count ├── Output/ │ ├── output.csv # Extracted and sorted data │ └── TextFiles/ # .txt summaries for oldest/youngest ├── Dependencies/ │ └── UiPathTeam.Utility.Activities.nupkg


---

## 📥 Input Format

### Example: `input.csv`

| Gender | Count |
|--------|-------|
| Male   | 5     |
| Female | 5     |

> ⚠ Each row indicates how many records of that gender should be generated.

---

## 📤 Output Files

### `output.csv`

| Firstname | Lastname | Email               | Age | Birthday   | Company |
|-----------|----------|---------------------|-----|------------|---------|
| Sarah     | Jensen   | sarah@evolvia.com   | 29  | 1995-01-23 | Evolvia |
| David     | Smith    | david@zenitro.com   | 52  | 1972-07-11 | Zenitro |

### `TextFiles/Sarah_Jensen.txt`


---

## ⚙️ Configurable Settings (`Config.xlsx`)

| Key                | Value                                 |
|--------------------|---------------------------------------|
| FNG_URL            | https://www.fakenamegenerator.com/    |
| Input_File_Path    | Input/input.csv                       |
| Output_File_Path   | Output/output.csv                     |
| Retry_Attempts     | 3                                     |
| Retry_Delay_ms     | 2000                                  |
| Notification_Email | your-email@domain.com                 |

> Configurations can be updated to suit different environments.

---

## 🚀 How to Run the Project

### 1. Prerequisites
- UiPath Studio 2022.10 or higher
- Chrome browser + UiPath Chrome extension

### 2. Setup Steps
- Download and extract the project ZIP.
- Open `project.json` in UiPath Studio.
- Place your `input.csv` file in the `Input/` folder.
- Use `Manage Packages` to import missing dependencies if prompted.
- Press **F5** to run `Main.xaml`.

---

## 🔄 Error Handling & Logging

- Uses `Try Catch` and `Retry Scope` for resilience.
- Exceptions are logged to `Logs/ExecutionLog.txt`.
- Screenshots taken during failures for visual debugging.
- Email alerts sent (if configured).

---

## 🧠 Highlights

- UI Automation of web browser elements
- Age slider and gender selection dynamically configured
- Reusable and modular workflow structure
- Scalable for queue-based execution with Orchestrator

---

## 🧪 Test & Validate

- Try changing the input counts to simulate larger data
- Use `Write Line` or logs to see data flowing through steps
- Modify `GenerateTextFiles.xaml` for other output formats

---
