Crypto ETL with Apache Airflow
This is a dynamic data pipeline project designed to keep tabs on the ever-changing world of cryptocurrency. Using Apache Airflow, this ETL pipeline pulls hourly snapshots of key metrics like price, market cap, and trading volume for top digital assets — then loads them into a PostgreSQL time-series database for analysis.

What This Project Does
This pipeline automates the full data journey — from pulling market data from the CoinGecko API to storing it in a structured format in your database. It's built to run hourly, giving you fresh insights around the clock.

  Core Highlights
-> Hourly crypto tracking for 15 top coins like BTC, ETH, SOL, and more

-> Captures price, volume, and market cap for each coin

-> Stores results in PostgreSQL under a crypto.crypto_prices table

-> Robust with retry mechanisms and failure alerts

-> Secrets like DB credentials managed securely via .env file

 Stack in Use
Tool	Purpose
Apache Airflow	Task orchestration & scheduling
Python 3.12	    Core language
CoinGecko API	  Real-time market data source
PostgreSQL	    Analytical data storage
psycopg2	      DB driver

Getting Started
Here’s how to spin up this pipeline on your local machine:

1. Clone the Repo
git clone https://github.com/your-username/crypto-etl-pipeline.git
cd crypto-etl-pipeline

3. Set Up the Virtual Environment
python -m venv venv
source venv/bin/activate

4. Initialize Airflow
airflow db init

6. Start the Web UI and Scheduler
airflow webserver --port 8080
airflow scheduler

How to Test the Pipeline
Open your browser and navigate to http://localhost:8080

Locate the DAG titled coin_price_etl_dag

Toggle it on and trigger a run

Open the logs to trace the data extraction and loading process

Where the Data Goes
You’ll find the processed data stored in the crypto.crypto_prices table, structured like this:

name	symbol	price	market_cap	total_volume	timestamp

Perfect for dashboards, trading models, or historical analytics.

Contributions Welcome
Want to improve the DAG, support new coins, or hook it into a visualization tool? Fork the repo, open a pull request, or drop a suggestion.

Get in Touch
Author: Kelly Kiprop
kipropkelly4@gmail.com

License
This project is open-sourced under the MIT License. Use it freely and modify as you see fit!
