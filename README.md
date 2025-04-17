# Stock-Market-Real-time-Data-Analysis
# 📈 Real-Time Stock Market Data Analysis

A Python-based project to ingest, store, and analyze real-time stock market data using Kafka and AWS (S3, Glue, Athena). Visualizations are created from queried Athena data using Python.

---

## 🔧 Tech Stack

- **Stream Processing**: Apache Kafka
- **Programming Language**: Python
- **Storage**: AWS S3
- **Data Catalog & Query**: AWS Glue Crawler, AWS Athena
- **Visualization**: Python (Pandas + Matplotlib/Plotly)

---

## ⚙️ Workflow

1. **Data Ingestion**: Real-time data is pushed into Kafka topics.
2. **Processing**: Kafka consumer reads data and writes it to S3 as CSV/JSON.
3. **Data Cataloging**: AWS Glue Crawler crawls the S3 bucket to create a table in AWS Glue Data Catalog.
4. **Querying**: Athena queries the Glue table for data analysis.
5. **Visualization**: Python scripts retrieve data using `boto3` + `PyAthena` and plot it using `matplotlib` or `plotly`.

---

## 📊 Visualization Code (Python)

```python
from pyathena import connect
import pandas as pd
import matplotlib.pyplot as plt

# Athena + S3 connection
s3_output = "s3://your-athena-query-results/"
conn = connect(s3_staging_dir=s3_output, region_name='us-east-1')

# Example query
query = """
SELECT symbol, price, timestamp
FROM stock_data
WHERE symbol = 'AAPL'
ORDER BY timestamp DESC
LIMIT 100
"""

df = pd.read_sql(query, conn)
df['timestamp'] = pd.to_datetime(df['timestamp'])

# Plotting
plt.figure(figsize=(12, 6))
plt.plot(df['timestamp'], df['price'], marker='o')
plt.title("AAPL Stock Price Over Time")
plt.xlabel("Timestamp")
plt.ylabel("Price")
plt.grid(True)
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()
