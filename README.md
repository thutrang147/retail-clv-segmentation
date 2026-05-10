# Retail CLV Segmentation

This project analyzes retail customer transactions to estimate Customer Lifetime Value (CLV) and segment customers based on predicted value and activity probability.

## Objective

The objective is to identify valuable customer groups and support data-driven marketing decisions such as retention, upselling, and win-back campaigns.

## Methodology

The analysis uses:

- **BG/NBD model** to predict future purchase frequency
- **Gamma-Gamma model** to estimate expected transaction value
- **K-Means clustering** to segment customers based on CLV and probability alive

## Dataset

Main fields used:

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
- Customer segments and cluster profile

## Customer Segments

| Segment | Meaning |
|---|---|
| VIP | High predicted value and high activity probability |
| Potential | Customers with growth potential |
| At Risk | Customers with declining activity probability |
| Lost | Low predicted value and low activity probability |

## Limitations

- `Customer_Name` is used as the customer identifier.
- `Total_Cost` is used as a proxy for monetary value.
- The segmentation is model-based and should be validated with business context.

## How to Run

```bash
pip install -r requirements.txt
jupyter notebook main.ipynb
```