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
## Architecture 
  
![Architecture](https://github.com/user-attachments/assets/121d230a-ce9e-4dc6-aac5-d4fd24e6fa87)


## ⚙️ Workflow

1. **Data Ingestion**: Real-time data is pushed into Kafka topics.
2. **Processing**: Kafka consumer reads data and writes it to S3 as CSV/JSON.
3. **Data Cataloging**: AWS Glue Crawler crawls the S3 bucket to create a table in AWS Glue Data Catalog.
4. **Querying**: Athena queries the Glue table for data analysis.
5. **Visualization**: Python scripts retrieve data using `boto3` + `pandas` and plot it using `matplotlib` or `seaborn`.

---
