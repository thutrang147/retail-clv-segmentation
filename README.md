# Retail CLV Segmentation

This project analyzes retail customer transaction data to estimate Customer Lifetime Value (CLV) and segment customers based on predicted value and activity probability.

## Objective

The objective of this project is to identify valuable customer groups and support data-driven marketing decisions, including retention, upselling, cross-selling, and win-back campaigns.

## Methodology

The analysis uses three main methods:

- **BG/NBD model** to predict future purchase frequency
- **Gamma-Gamma model** to estimate expected transaction value
- **K-Means clustering** to segment customers based on CLV and probability alive

## Dataset

The raw dataset is not included in this repository because it exceeds GitHub's file size limit.

The dataset can be downloaded from Kaggle:

https://www.kaggle.com/datasets/prasad22/retail-transactions-dataset

To reproduce the analysis, download the dataset and save it as:

```text
data/raw/data.csv
```

Main fields used in the analysis:

- `Customer_Name`
- `Date`
- `Total_Cost`
- `Total_Items`

## Outputs

The notebook generates:

- RFM summary
- Predicted future transactions
- Probability alive
- 6-month CLV estimate
- Customer segments
- Cluster profile and business interpretation

## Customer Segments

| Segment | Meaning |
|---|---|
| VIP | High predicted value and high activity probability |
| Potential | Customers with growth potential |
| At Risk | Customers with declining activity probability |
| Lost | Low predicted value and low activity probability |

## Limitations

- `Customer_Name` is used as the customer identifier, which may cause duplication if different customers share the same name.
- `Total_Cost` is used as a proxy for monetary value.
- The estimated CLV should be interpreted as a model-based customer value indicator rather than exact profit-based lifetime value.
- Customer segments are generated using unsupervised clustering and should be interpreted with business context.

## How to Run

Install the required libraries:

```bash
pip install -r requirements.txt
```

Open the notebook:

```bash
jupyter notebook main.ipynb
```

Then run all cells from top to bottom.