# Discount and Profitability Analysis (Global Superstore)

I wanted to find out at what discount level a store starts losing money, and whether it is the discount that causes the loss or just the products.

## Data

[Global Superstore dataset](https://www.kaggle.com/datasets/rohitgrewal/global-superstore-data) from Kaggle, a sample dataset of a made-up global retail store. It has about 51,000 order lines with sales, discount and profit for each one. This is not real company data.

## Process (in Excel)

1. Checked the data: every Row ID is unique, and there are no blank cells in Sales, Quantity, Discount, Profit, Category or Sub-Category.
2. Worked out the baseline for the whole store: total sales about 12.64 million, total profit about 1.47 million, so a profit margin of 11.6%.
3. Grouped the discounts into four bands with a nested IF formula: None (0), Low (above 0 up to 20%), Medium (above 20% up to 40%) and High (above 40%). There are 29,009, 10,953, 4,367 and 6,961 rows in the bands.
4. Used pivot tables to get sales, profit and profit margin for each band, and then each sub-category within each band.

## Findings

| Discount band | Profit margin |
|---|---|
| None | 25.3% |
| Low (up to 20%) | 13.7% |
| Medium (20% to 40%) | -17.3% |
| High (above 40%) | -74.1% |

- Margin falls as the discount goes up. Even a small discount roughly halves the margin, and above about 20% the store loses money.
- All 17 sub-categories make a profit with no discount and with up to 20% discount, and all of them lose money above 20%. So the loss follows the discount, not just the type of product.
- Tables, Bookcases and Phones lose the most under discounts above 20% (about 133K, 90K and 87K).

## Limitations

- The band edges (20% and 40%) are my choice. The data shows that profit turns to loss somewhere around 20%, but not the exact point.
- The sub-category check shows the pattern is consistent. It does not prove that the discount alone causes the loss, because things like region and order size could also differ.
- It is a sample dataset, so the numbers are for practising the method, not for a real business.
