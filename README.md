# Genuine Excel Metadata Cleaner & Spoofer v2.6

A lightweight, powerful Windows desktop tool designed to protect your digital privacy by erasing automated signatures from Excel files. It converts programmatically generated or modified spreadsheets (from Python openpyxl/pandas or LibreOffice Calc) into **100% authentic, human-made Microsoft Excel 365 documents**.

[🚀 DOWNLOAD THE READY-TO-RUN .EXE DIRECTLY FROM THIS REPOSITORY](./ExcelMetadataCleaner.exe)

---

## The Problem with Automated Spreadsheets
Files generated or modified via Python libraries or alternative office suites leave deep, permanent structural fingerprints inside the OpenXML code. Advanced AI detectors, school grading systems, and corporate auditors analyze these invisible markers:
* **Custom Default Styles:** LibreOffice/openpyxl leave specific 56-color palettes, default cell ranges, and font setups.
* **Page Layout Quirks:** Automated files often contain dead giveaways like exact 300 DPI page setups, specific 1.3 cm header margins, and missing printer structures (`calcChain.xml`).
* **Perfect Timestamps:** Scripts usually save the file instantly, leaving identical seconds on creation and modification times, and a revision history of 0 or 1.

Even if you fake the basic metadata text, **the structural DNA reveals the automation instantly.**

---

## The Solution: "Excel-Ghost" Engine
This tool does not just run a basic text search-and-replace on the XML. Instead, it utilizes native Microsoft Excel components to execute a clean data transplantation:

1. **Pure Data Extraction:** It securely boots a headless, invisible Excel instance to extract *only* the raw cell values and formulas from the source file.
2. **Fresh Canvas Creation:** It generates a brand-new Excel 365 spreadsheet using the native Microsoft engine, inheriting the official **Office 2023 theme (Aptos Narrow)**.
3. **Humanization Injection:** It passes the data into the new canvas while intentionally mimicking human user interaction (randomized column widths, offsets, leaving the active cell cursor on a logical area like `D9`).
4. **Deep Metadata Spoofing:** It randomizes realistic modification time intervals (with completely distinct seconds) and clean revision tracking counters under your custom Author name and Language code (`fi-FI`, `en-US`, etc.).

The final output contains **zero traces of code generation or LibreOffice history**, passing any deep digital forensics audit perfectly.

---

## How to Use the Executable

No Python installation or setup required. 

1. Download **`ExcelMetadataCleaner.exe`** directly from the root of this repository.
2. Run the application on a Windows machine with Microsoft Excel installed.
3. Click **"Selaa tiedostoa..."** and select your `.xlsx` file.
4. Customize the **Author name** and **Document language**.
5. Click **"Aja Täydellinen Siivous"** and choose where to save your pristine file.

---

## For Developers (Source Code)

If you wish to run or modify the project from source, you can find `excel_cleaner_gui.py` and `convert.py` in this repository.

### Requirements:
* Windows OS
* Microsoft Excel installed (required for the `xlwings` COM API automation)
* Python 3.10+

### Setup a Virtual Environment:
```bash
python -m venv venv
.\venv\Scripts\Activate.ps1
pip install xlwings pyinstaller
```

### Running the App:
```bash
python excel_cleaner_gui.py
```

---

## License & Privacy
This tool is open for personal and educational use. It processes everything locally on your machine—**no file contents or metadata are ever uploaded to any external server.**

