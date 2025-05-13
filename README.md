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
## Stock Visualization
---
        index  count
0       N225     45
1        NYA     41
2     GSPTSE     34
3       IXIC     30
4      GDAXI     28
5       TWII     20
6        HSI     20
7       SSMI     15
8  399001.SZ     15
9       N100     13

![image](https://github.com/user-attachments/assets/905166ca-a558-42d7-95a1-be374f8d6ddd)


## Dataset Used
The Dataset used for the project :
https://github.com/KaranVeer72/Stock-Market-Real-time-Data-Analysis/blob/main/indexProcessed.csv
