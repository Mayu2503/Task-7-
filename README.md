# Task-7
# Sales Data Management with SQLite

This project demonstrates how to create and manage a simple `sales` table using SQLite and Python. The project is implemented in a Jupyter Notebook named `Elevate.ipynb`.

## 📌 Table Schema

The table created is named `sales`, and it includes the following fields:

- `id`: Integer, Primary Key, Auto-incremented
- `ITEM`: Text, Name of the item
- `Quantity`: Integer, Number of units sold
- `price_per_unit`: Integer, Price of each item

## 🛠️ Features

- Create a sales table if it does not exist
- Insert sales records into the database
- Fetch and display sales records

## 📦 Requirements

- Python 3.x
- SQLite (via `sqlite3` module, comes pre-installed with Python)
- Jupyter Notebook (optional, for running `Elevate.ipynb`)

## ▶️ How to Run

1. Clone this repository or download the files.
2. Open the `Elevate.ipynb` file in Jupyter Notebook.
3. Run the cells to:
   - Connect to SQLite
   - Create the `sales` table
   - Perform data operations (insert, fetch, etc.)

## 📝 Example Code Snippet

```python
import sqlite3

conn = sqlite3.connect("salesdata.db")
cursor = conn.cursor()

cursor.execute("""
    CREATE TABLE IF NOT EXISTS sales (
        id INTEGER PRIMARY KEY AUTOINCREMENT,
        ITEM TEXT,
        Quantity INTEGER,
        price_per_unit INTEGER
    )
""")

# Example insert
cursor.execute("INSERT INTO sales (ITEM, Quantity, price_per_unit) VALUES (?, ?, ?)",
               ("Apples", 10, 2))

conn.commit()
conn.close()
