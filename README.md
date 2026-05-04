# Assignment 1 - Transliteration Accuracy Testing

## IT3040 – ITPM | BSc (Hons) in Information Technology | Year 3

This project automates testing of the Chat Sinhala transliteration function available at:
**https://www.pixelssuite.com/chat-translator**

The automation uses Playwright to test 50 Singlish input test cases and records the actual output and pass/fail status in an Excel file.

---

## Prerequisites

- Python 3.11 or 3.12
- Google Chrome (recommended) or Chromium (installed via Playwright)
- Windows OS

---

## Project Structure

```
test_automation/
│
├── test_automation.py          # Main Playwright automation script
├── Assignment 1 - Test cases.xlsx  # Test cases with results
└── README.md                   # This file
```

---

## Installation

Open **Command Prompt** and navigate to the project folder:

```bash
cd /d D:\test_automation
```

Install the required dependencies (one-time only):

```bash
pip install -U pip
pip install playwright openpyxl
playwright install
```

---

## Running the Tests

Make sure the Excel file is **closed** before running. Then run:

```bash
python test_automation.py --excel "Assignment 1 - Test cases.xlsx" --url "https://www.pixelssuite.com/chat-translator" --wait-ms 5000 --type-delay-ms 80 --slow-mo-ms 200 --save-every 1 --keep-open
```

### Command Arguments

| Argument | Description |
|---|---|
| `--excel` | Path to the Excel test cases file |
| `--url` | URL of the web application to test |
| `--wait-ms` | Wait time in milliseconds after each translation |
| `--type-delay-ms` | Delay between keystrokes when typing input |
| `--slow-mo-ms` | Slow motion delay for browser actions |
| `--save-every` | Save results to Excel after every N test cases |
| `--keep-open` | Keep the browser open after all tests complete |

---

## Checking Results

After the script finishes:

1. Press **CTRL+C** to stop the browser
2. Open `Assignment 1 - Test cases.xlsx`
3. Verify the **Actual output** and **Status** columns are filled in correctly

---

## Test Case Structure

The Excel file contains the following columns:

| Column | Description |
|---|---|
| TC ID | Test case ID (all begin with "Neg_") |
| Input length type | S (≤30 chars), M (31–299 chars), L (300–450 chars) |
| Input | Singlish input text |
| Expected output | Correct Sinhala translation |
| Actual output | Output recorded by automation |
| Status | PASS or FAIL |
| Singlish input types covered | Category of Singlish input type |
| Evidence or rationale | Justification for the input type classification |
