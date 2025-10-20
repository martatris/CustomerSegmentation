# RFM Customer Segmentation Project

## Overview
This project performs **customer segmentation** using **RFM (Recency, Frequency, Monetary)** analysis. It reads an Excel dataset, computes RFM metrics, assigns scores, segments customers, and optionally performs K-Means clustering.

## Dataset
- **File Name:** `Online Retail.xlsx`
- **Columns:**
  - InvoiceNo
  - StockCode
  - Description
  - Quantity
  - InvoiceDate
  - UnitPrice
  - CustomerID
  - Country

## Steps
1. Load the dataset and clean it:
   - Remove rows with negative or zero Quantity and UnitPrice.
   - Drop rows with missing CustomerID.
2. Convert `InvoiceDate` to datetime.
3. Compute **TotalPrice** column (`Quantity * UnitPrice`).
4. Aggregate data per customer to compute **RFM metrics**:
   - **Recency:** Days since last purchase.
   - **Frequency:** Number of unique invoices.
   - **MonetaryValue:** Total spending.
5. Assign **RFM scores (1-5)** using `pd.qcut` with `duplicates='drop'`.
6. Combine RFM scores into **RFM_Score**.
7. Segment customers into categories:
   - Champions
   - Loyal
   - Potential Loyalist
   - At-risk
   - Hibernating
   - Others
8. Optionally, scale features and perform **K-Means clustering**.
9. Compute **Silhouette Score** for cluster quality.
10. Analyze and visualize segments using scatterplots.

## Dependencies
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn

Install via pip if needed:
```
pip install pandas numpy scikit-learn matplotlib seaborn openpyxl
```

## Usage
1. Place `Online Retail.xlsx` in the project folder.
2. Run the Python script `imagingGen.py`.
3. Output:
   - Customer segmentation summary.
   - Silhouette score for K-Means clustering.
   - Scatterplot visualization of segments.

## Notes
- The code handles duplicate values in RFM scoring using `duplicates='drop'`.
- K-Means clustering is optional and used for additional insights.
- The visualization helps in understanding customer distribution across Monetary vs Frequency.
