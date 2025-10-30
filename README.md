
# Python-PostgreSQL ETL Pipeline

## 📌 Project Overview
This project implements an **ETL (Extract, Transform, Load)** pipeline using **Python** and **PostgreSQL** to process and analyze JSON log data. It simulates a real-world data engineering workflow — extracting raw event data, transforming it into a relational model, and loading it into a PostgreSQL database for analytical queries.

The project was inspired by a data warehouse use case similar to what streaming platforms like Spotify or Netflix would use to analyze user activity.

---

## 🚀 Key Features
- **Automated ETL Pipeline** to extract JSON log data.
- **Schema Design & Table Creation** for a relational database model.
- **Data Transformation** using Python and SQL.
- **Efficient Data Loading** into PostgreSQL tables.
- **Validation & Testing** through Jupyter notebooks.

---

## 🛠️ Tech Stack
- **Programming Language:** Python 3.x  
- **Database:** PostgreSQL  
- **Libraries:** psycopg2, pandas, json, os, glob  
- **Tools:** Jupyter Notebook, SQL, Git

---

## 🧩 Project Structure
```
Python-PostgreSQL ETL/
│
├── create_tables.py          # Script to define and create PostgreSQL tables
├── etl.py                    # Main ETL script for extracting, transforming, and loading data
├── sql_queries.py            # SQL queries for table creation and data insertion
├── etl.ipynb                 # ETL pipeline demonstration notebook
├── test.ipynb                # Validation and testing notebook
├── data/
│   └── log_data/             # Folder containing JSON input files
├── database.cfg.template     # Template for database configuration (user, password, host, dbname)
├── requirements.txt          # Python dependencies
└── .gitignore
```

---

## 🧠 Data Model
The project uses a **Star Schema** design with the following tables:

**Fact Table**
- `songplays` – records in event data associated with song plays.

**Dimension Tables**
- `users` – user information.  
- `songs` – song details.  
- `artists` – artist information.  
- `time` – timestamps of records broken down into time units.

This schema optimizes query performance for analytical workloads.

---

## ⚙️ ETL Process
1. **Extract** JSON files from the `data/log_data/` directory.  
2. **Transform** data — clean, structure, and map relationships (user, song, artist).  
3. **Load** the transformed data into PostgreSQL tables using `psycopg2`.  

You can visualize and test the pipeline through `etl.ipynb` and `test.ipynb`.

---

## 💻 Setup Instructions
1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/Python-PostgreSQL-ETL.git
   cd Python-PostgreSQL-ETL
   ```

2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Configure database:**
   - Copy `database.cfg.template` → `database.cfg`
   - Update your PostgreSQL credentials inside the file.

4. **Run scripts:**
   ```bash
   python create_tables.py
   python etl.py
   ```

---

## 🧾 Example Output
After successful execution, PostgreSQL will contain structured tables populated with data from JSON files. You can query them, for example:
```sql
SELECT * FROM songplays LIMIT 5;
```

---

## 🧭 Future Enhancements
- Integrate AWS S3 for data storage.  
- Automate with Apache Airflow.  
- Add logging and monitoring features.  
- Implement data validation before loading.

---

## 🏁 Conclusion
This project demonstrates practical data engineering skills including schema design, ETL automation, and PostgreSQL integration. It forms a strong foundation for building scalable analytics pipelines in real-world environments.
