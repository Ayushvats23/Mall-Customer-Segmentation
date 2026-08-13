# Mall-Customer-Segmentation

This project performs **unsupervised machine learning (K-Means Clustering)** on the classic **Mall Customers dataset** to segment customers into distinct groups based on their income and spending behavior. These segments can help a business:

- Identify high-value customers to target with premium offers
- Spot low-engagement customers who need re-activation campaigns
- Design personalized marketing strategies for each customer group

---

Dataset

The dataset (`Mall_Customers.csv`) contains **200 customer records** with the following features:

| Column | Description |
|---|---|
| `CustomerID` | Unique ID assigned to each customer |
| `Gender` | Male / Female |
| `Age` | Customer's age |
| `Annual Income (k$)` | Customer's annual income (in thousand $) |
| `Spending Score (1-100)` | Score assigned by the mall based on customer spending behavior |

---

Workflow

The notebook follows a complete, structured ML pipeline:

1. **Exploring the Dataset**
- Checked shape, data types, summary statistics, and missing values

   2. **Data Cleaning**
- Dropped the non-informative `CustomerID` column

   3. **Data Visualization & EDA**
- **Gender distribution** — Female customers outnumber Male customers
- **Age distribution** — Three dominant shopper age groups identified: `18–23`, `28–38`, and `45–50`
- **Age vs Spending Score** — High spenders (score > 65) are mostly aged 15–42, with more females than males
- **Annual Income vs Spending Score** — Revealed 5 natural visual clusters in customer behavior

   4. **Finding Optimal Clusters — Elbow Method**
- Used **WCSS (Within-Cluster Sum of Squares)** across `k = 1 to 10`
- Optimal number of clusters identified: **k = 5**

   5. **Feature Scaling**
- Applied `StandardScaler` since K-Means relies on distance-based calculations

   6. **Model Building**
- Trained a **K-Means (k-means++)** model on `Annual Income` and `Spending Score`
- Visualized the resulting 5 customer clusters

---

 Customer Segments Identified

| Cluster | Segment | Business Insight |
|---|---|---|
| 🟡 Cluster 1 | Low Income, Low Spending | Budget-conscious — minimal marketing investment needed |
| 🔵 Cluster 2 | Average Income, Average Spending | Stable segment — moderate offers/loyalty programs |
| 🟢 Cluster 3 | High Income, Low Spending | Untapped potential — gather feedback, improve engagement |
| 🟠 Cluster 4 | Low Income, High Spending | Price-sensitive but loyal — reward with deals/discounts |
| 🔴 Cluster 5 | High Income, High Spending | **Most valuable customers** — target with premium/new product alerts |

---

 Tech Stack

- **Python 3**
- **Pandas / NumPy** — Data manipulation
- **Matplotlib / Seaborn** — Data visualization
- **Scikit-learn** — K-Means clustering & feature scaling

---

 Getting Started

 1. Clone the repository
```bash
git clone https://github.com/<Ayushvats23>/Mall-Customer-Segmentation.git
cd Mall-Customer-Segmentation
```

 2. Install dependencies
```bash
pip install numpy pandas matplotlib seaborn scikit-learn jupyter
```

 3. Run the notebook
```bash
jupyter notebook Mall_Customer_Segmentation.ipynb
```

---

 Sample Visualizations

The notebook includes:
- Gender count plot
- Age distribution histogram
- Age vs Spending Score scatter/joint plots
- Annual Income vs Spending Score scatter/joint plots
- Elbow Method plot (WCSS vs K)
- Final K-Means cluster visualization

---

 Project Structure

```
├── Mall_Customer_Segmentation.ipynb   # Main analysis notebook
├── Mall_Customers.csv                  # Dataset
└── README.md                           # Project documentation
```

---

 Future Improvements

- Incorporate `Age` and `Gender` as additional clustering features
- Compare K-Means results with **Hierarchical Clustering / DBSCAN**
- Deploy an interactive dashboard (Streamlit/Plotly Dash) for cluster exploration
- Use **Silhouette Score** to further validate cluster quality

---

 License

This project is open-source and available under the [MIT License](LICENSE).

---

 Acknowledgements

Dataset sourced from the widely-used **Mall Customer Segmentation** dataset (commonly available on Kaggle).
