# Shop Management System

A desktop shop/grocery management application built with **Python (Tkinter)** and **SQLite**. It lets a shopkeeper record stock and generate simple bills for sales, with everything stored locally in a SQLite database.

##  Features

- 📦 **Stock Management** — add new stock entries (date, product, price, quantity) and view all recorded stock
- 🧾 **Billing** — select quantities for four preset products and generate an itemized bill with totals
- 📊 **Sales History** — view every past sale logged to the database
- 💾 **Local Storage** — all data is saved in a local SQLite file (`shopManagement.db`), no server or internet required
- 🖥️ **Tabbed UI** — simple two-tab interface (Stock / Sell) built with `ttk.Notebook`

##  Tech Stack

| Layer | Technology |
|---|---|
| GUI | Tkinter + ttk |
| Date Picker | tkcalendar |
| Database | SQLite (via Python's built-in `sqlite3`) |
| Language | Python 3 |

##  How It Works

1. **Stock tab** — enter a date, product name, price, and quantity, then click **Add** to insert it into the `stock` table. Click **View Stock** to list everything currently recorded.
2. **Sell tab** — four products are pre-listed with fixed prices (Maggie, Biscuits, Instant Noodles, Rice). Enter the quantity sold for each, then click **Bill** to:
   - Calculate line totals and a grand total
   - Print an itemized receipt in the text area
   - Save each sold item into the `sell` table
3. Click **View All Sellings** to see the full sales history pulled from the database.

##  Requirements

- Python 3.x
- `tkcalendar` (only external dependency — Tkinter and sqlite3 ship with Python)

##  Installation & Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/MUKTHAR27/grocery_management_system.git
   cd grocery_management_system
   ```

2. **Install dependencies**
   ```bash
   pip install tkcalendar
   ```

3. **Run the application**
   ```bash
   python main.py
   ```

   A `shopManagement.db` SQLite file will be created automatically in the project folder on first run.

##  Database Schema

**`stock` table**
| Column | Type |
|---|---|
| date | string |
| product | string |
| price | number |
| quantity | number |

**`sell` table**
| Column | Type |
|---|---|
| date | string |
| product | string |
| price | number |
| quantity | number |
| total | number |

##  Future Improvements

- Replace the four hardcoded products with a dynamic product list pulled from the `stock` table
- Add stock deduction when a sale is made (currently stock and sales aren't linked)
- Input validation (e.g. prevent non-numeric entries, negative quantities)
- Editable/deletable stock and sales records
- Export bills/reports to PDF or CSV
- Search and filter for stock and sales history

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you'd like to change.

## 📄 License

This project is open-source and available under the MIT License.
