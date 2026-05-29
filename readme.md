# 🧾 Invoice Generation App

A Python automation tool that reads invoice data from Excel spreadsheets and automatically generates professional, formatted PDF invoices — complete with itemised tables, totals, and company branding.

---

## 📋 Features

- Batch processes multiple Excel invoice files in one run
- Automatically extracts invoice number and date from the filename
- Generates a clean, formatted PDF for each invoice including:
  - Invoice number and date header
  - Itemised product table (ID, name, quantity, unit price, total)
  - Automatically calculated grand total row
  - Total price summary sentence
  - Company name and logo
- Outputs PDFs into a dedicated `/PDFs` folder

---

## 🛠️ Tech Stack

| Library | Purpose |
|---|---|
| `pandas` | Reading and processing Excel invoice data |
| `fpdf2` | Generating formatted PDF documents |
| `glob` | Batch file discovery |
| `pathlib` | File path handling |

---

## 🚀 Getting Started

### Prerequisites

- Python 3.x
- pip

### Installation

1. **Clone the repository**

```bash
git clone https://github.com/PeterTZN/Invoice_Generation_APP.git
cd Invoice_Generation_APP
```

2. **Create and activate a virtual environment**

```bash
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
```

3. **Install dependencies**

```bash
pip install -r requirements.txt
```

---

## 📁 Project Structure

```
Invoice_Generation_APP/
│
├── invoices/               # Place your Excel (.xlsx) invoice files here
│   └── 10001-2023.01.18.xlsx
│
├── PDFs/                   # Generated PDF invoices are saved here
│
├── main.py                 # Main script
├── pythonhow.png           # Company logo used in PDFs
├── requirements.txt
└── .gitignore
```

---

## 📄 Excel File Format

Each `.xlsx` file in the `/invoices` folder must:

- Be named in the format: `{invoice_number}-{date}.xlsx` (e.g. `10001-2023.01.18.xlsx`)
- Contain a sheet named **"Sheet 1"**
- Have the following columns:

| Column | Description |
|---|---|
| `product_id` | Unique product identifier |
| `product_name` | Name of the product |
| `amount_purchased` | Quantity purchased |
| `price_per_unit` | Unit price |
| `total_price` | Line total (quantity × unit price) |

---

## ▶️ Usage

Place your Excel invoice files in the `/invoices` folder, then run:

```bash
python main.py
```

A PDF will be generated for each `.xlsx` file and saved to the `/PDFs` folder with the same filename.

---

## 📌 Roadmap

- [ ] Add support for custom company name and logo via config file
- [ ] Add currency formatting to price fields
- [ ] HTML invoice output option
- [ ] Command-line arguments for input/output directories
- [ ] Email invoices directly to clients

---

## 🙏 Acknowledgements

- [fpdf2](https://pyfpdf.github.io/fpdf2/)
- [pandas](https://pandas.pydata.org/)

---

## 👨‍💻 Author

**Peter Thomson**
- GitHub: [@PeterTZN](https://github.com/PeterTZN)

---

## 📄 Licence

This project is open source and available under the [MIT License](LICENSE).