# Power BI Data Analytics Workshop

Documentation curated by Girisha Malni N, Vishalini S, Syed Ameen G, Osho V - dated 15/9/2026 

##  Why Power BI over Excel?

| Feature | Excel | Power BI |
|---|---|---|
| Data handling | Cell-based | Data-model based |
| Query performance | Limited at scale |  VertiPaq + In-memory |
| Data preparation | Formulas / Power Query | Power Query / ETL |
| Calculations | Excel Functions | DAX + Measures |
| Real-time analytics | Limited | Streaming / Fabric |
| Python | Possible | Integrated workflow |
| Large datasets | Worksheet limitations | Scalable Semantic Models |

---

# 1.  Fast Queries — VertiPaq

Power BI Import mode uses **VertiPaq**, an in-memory, columnar storage engine.

### Why is it fast?

- **Column-wise storage**
- **Data compression**
- Compressed data stored in **RAM**
- Queries scan only the **required columns**

```text
Traditional:
Row → Row → Row → Row

VertiPaq:
Column A → Compressed → RAM
Column B → Compressed → RAM
Column C → Compressed → RAM
```

> **Columnar Storage + Compression + RAM = ⚡ Fast Analytics**

---

# 2. Dynamic & Real-Time Analytics

Modern analytics is not just:

```text
CSV → Excel → Report
```

It can be:

```text
Data Sources
     ↓
    ETL
     ↓
Data Model
     ↓
 Power BI
     ↓
Dashboard / Alerts
```

### Possible Sources

- IoT / Sensors
- APIs
- Applications
- Streaming events
- Operational systems

> **Move from "What happened?" → "What is happening now?"**

---

# 3. Power Query + Python

## Power Query = ETL

**Extract → Transform → Load**

Used for:

- Data cleaning
- Removing duplicates
- Handling missing values
- Changing data types
- Merge / Append
- Filtering
- Reshaping data

### Python Integration

```text
Power Query
     ↓
Clean Data
     ↓
Python
     ↓
Time-Series Model
     ↓
Forecast
     ↓
Power BI Dashboard
```

## Time-Series Forecasting

| Model | Concept |
|---|---|
| **ARIMA** | Autoregressive + Integrated + Moving Average |
| **SARIMA** | ARIMA + Seasonality |
| **SARIMAX** | SARIMA + External Variables |

### Excel vs Python

**Excel:** Built-in forecasting such as **ETS** and linear forecasting.

**Python:** More flexibility for:

- ARIMA
- SARIMA
- SARIMAX
- Custom statistical models
- Machine Learning

> **Excel gives you built-in forecasting. Python gives you modelling freedom.**

---

# 4. DAX vs Excel Functions

## Excel

```excel
=SUM(B2:B100)
```

Think:

```text
Cells → Ranges → Formulas
```

## DAX

```DAX
Total Sales =
SUM(Sales[Sales])
```

Think:

```text
Tables
   ↓
Relationships
   ↓
Filter Context
   ↓
Measures
```

## ⭐ Key DAX Concept — `CALCULATE()`

```DAX
South Sales =
CALCULATE(
    [Total Sales],
    Sales[Region] = "South"
)
```

> **CALCULATE = Change the filter context → Calculate**

This is one of the biggest conceptual differences between **Excel formulas and DAX**.

---

# 5. Big Data & Capacity

## Excel

### Worksheet Limit

- **1,048,576 rows**
- **16,384 columns**


## Power BI

- Standard semantic model: **1 GB default size**
- Larger models are possible with **Microsoft Fabric / Premium capacity**
- Large Semantic Models support substantially larger datasets
- Actual limits depend on **capacity, storage mode and architecture**

> **Big data isn't just about row count. Storage, compression, modelling and architecture matter.**

---

# Workshop Mental Model

```text
        RAW DATA
            ↓
       POWER QUERY
            ↓
       DATA MODEL
            ↓
           DAX
            ↓
        ANALYTICS
            ↓
        POWER BI
            ↓
        DECISIONS
```

> **Raw Data → Clean → Model → Calculate → Analyze → Visualize → Decide**
