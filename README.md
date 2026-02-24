This is a very comprehensive breakdown of your script's logic. I have translated and organized your instructions into a professional, structured GitHub **README.md** format.

This version uses clear technical English while preserving your specific warnings and operational steps.

---

# Treasury-Management & Finance Operations Toolkit

**Automating finance operations:** High-performance scripts and utilities for account reconciliation, ledger management, general forecasting, and automated financial data processing.

This toolkit was developed with **ERP (Enterprise Resource Planning)** logic in mind, specifically designed to clean, manage, and forecast data for seamless integration with **Power BI** dashboards.

---

## 🛠 Prerequisites & Installation

To run these scripts, you must have Python installed along with the following dependencies. You can install them all at once using:

```bash
pip install pandas numpy openpyxl xlsxwriter faker

```

### Required Libraries

The script utilizes the following "bibles" (libraries) for data processing and Excel formatting:

* **Pandas & NumPy:** Core data manipulation and matrix calculations.
* **Openpyxl & XlsxWriter:** Advanced Excel engine for formatting and sheet management.
* **Faker:** Generation of synthetic data for testing.
* **DateTime:** Management of financial periods and DFC timelines.

---

## ⚠️ Important Warning
**Do not modify or remove any structural code from the script.** Deleting segments of the logic will disrupt the automation flow and may cause errors in data integrity.

---

## ⚙️ Configuration (Customizable Sections)

You can align the script to your specific business rules within the **"CÓDIGOS AUXILIARES"** section. Examples of customizable fields include:
  * **Mapping Categories:** Change `RECEITA` and `DESPESA` to `REVENUE` and `LIABILITIES`.
  * **Banking Data:** Update bank names and account IDs to match your institution.
  * **Entities (Entidades):** Customize the list of suppliers or clients as needed.
  * **Report Name:** By default, the script looks for `Relatório Financeiro 100k.xlsx`. *It is recommended to keep this filename to avoid pathing errors.*

---

## 🚀 Operational Workflow (Step-by-Step)

### 1. Initial Selection
Choose the module you wish to work in: `RECEITA` (Income) or `DESPESA` (Expenses). The input is case-insensitive.

### 2. Period Filtering
Select the date range for your current task.

> **Tip:** You can create a new cell (`+ CODE`) and type `sheet` to preview the filtered dataframe at any time.

### 3. Data Maintenance & Forecasting
Before generating forecasts, you must choose an action for the current dataset:
* **`[a]dicionar`**: Add a new entry/line.
* **`[e]ditar`**: Modify the most recent entry.
* **`[u]ltima`**: Adjust a specific line using its Index number.

*Note: The script protects the integrity of the database by forbidding edits to specific calculated columns.*

### 4. DFC (Daily Cash Flow Statement) Adjustments
To adjust or update the DFC, follow these steps:
1. Enter the target date in **`YYYY-MM-DD`** format.
2. Choose the transaction type:
  * `[0] Conta Garantida - Limite` (Guaranteed Account/Credit Line)
  * `[1] Transferências Recebido e Enviado` (Internal Transfers)
3. If choosing **[1]**, select the bank account using the numerical representation provided.
4. Input the transaction values.

### 5. Final Processing & Export
Once confirmed, the script performs the following:
  * **Formatting:** Standardizes dates, values, and account numbers.
  * **Categorization:** Automatically assigns entries to `OPERATIONAL`, `FINANCIAL`, `FISCAL`, or `OTHER` categories.
  * **Database Sync:** Sends data to the master file.
  * **Auto-Generation:** Builds sheets for the next 3 business days (skipping weekends/holidays).
  * **Reporting:** Generates a summary file for team sharing (14-day DFC if before mid-month; 30-day DFC if after).

---

## 📊 Data Formats
* **Dates:** `YYYY-MM-DD`
* **Values:** Standard numeric format for financial calculation.
* **Categorization (Revenue):** Revenue, Reversal (Estorno), Return (Devolução), and Loans.
* **Categorization (Expenses):** Operational, Financial, Fiscal, and Others.

---

### How to use this for Power BI
This script ensures that the underlying Excel database is always "clean" and correctly categorized. Simply refresh your **Power BI** dashboard after running the script to see the updated forecasts and DFC analysis.
