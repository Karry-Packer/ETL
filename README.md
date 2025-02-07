This project demonstrates an ETL (Extract, Transform, Load) pipeline that fetches real-time cryptocurrency data from the CoinGecko API, processes and cleans the data using Pandas, and stores it in a PostgreSQL database. The pipeline is fully automated using Cron Jobs (Linux) / Task Scheduler (Windows) for scheduled execution.

Tech Stack & Tools Used
- Python (requests, pandas, psycopg2)
- PostgreSQL (Database for storing records)
- CoinGecko API (Free public API for cryptocurrency data)
- Cron Jobs / Task Scheduler (For automation)

  ETL Pipeline Workflow
1️⃣ Extract: Fetches top 10 cryptocurrencies by market cap using the CoinGecko API.
2️⃣ Transform: Cleans the data using Pandas (removes null values, selects key fields).
3️⃣ Load: Stores the transformed data into a PostgreSQL database.
4️⃣ Automate: Uses Cron Jobs (Linux) or Task Scheduler (Windows) to schedule daily execution.

Step 1: Install Dependencies
pip install -r requirements.txt

Step 2: Set Up PostgreSQL Database
CREATE DATABASE crypto_data;

CREATE TABLE IF NOT EXISTS crypto_prices (
    id SERIAL PRIMARY KEY,
    coin_id TEXT,
    symbol TEXT,
    name TEXT,
    current_price NUMERIC,
    market_cap BIGINT,
    total_volume BIGINT
);

Step 3: Run the ETL Pipeline
0 0 * * * /usr/bin/python3 /path/to/etl_pipeline.py

 Step 4: Automate Execution (Optional)
 0 0 * * * /usr/bin/python3 /path/to/etl_pipeline.py


