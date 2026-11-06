# Online Retail Sales Analysis

This project looks at a year of sales from a UK online gift shop. It tries to answer four plain questions: where the money comes from, which products sell, when sales rise, and which customers keep coming back. All of the work was done in Google Sheets, using pivot tables, lookups and charts.

## What is in this repository

- [Online-Retail-Analysis-Report.pdf](Online-Retail-Analysis.pdf): the written report, with the method, findings and recommendations.
- [Summary workbook](https://docs.google.com/spreadsheets/d/1xm2tOPYfO1GrGpf1K7RM5jFjmSy5kAdMr2s3pnsiYlQ/edit?usp=sharing): the final tables and charts for each question, one tab per question.
- [Online Retail Analysis - summary.xlsx](Online%20Retail%20Analysis%20-%20summary.xlsx): a downloaded copy of the workbook, in case the Google Sheets link stops working. Charts may look slightly different in Excel.

## The four questions and what the data said

**1. Where does the revenue come from?**
The UK brings in 84.7% of net revenue, which is £8.27M out of £9.76M. Outside the UK, the five biggest markets are the Netherlands, Ireland, Germany, France and Australia. Together they make up about 71% of the remaining £1.49M.

**2. Which products sell the most, and do cheap products sell more?**
Two products looked like top sellers until the returns were counted. One dropped from £168,470 to £0 and the other from £81,701 to £4,221, because huge orders had been cancelled. After that fix, the best sellers by quantity are mostly cheap items. Among the 50 best sellers, though, price says very little about how much a product sells (correlation of -0.11).

**3. When do sales rise, and does it match a festival?**
Revenue is fairly flat until August, then climbs and peaks in November at £1.42M, about double a normal summer month. The rise comes from more orders (84% more than the summer average), while the size of the average order barely moved. The timing fits Christmas stocking. Easter shows nothing.

**4. Who keeps buying?**
Of 4,334 customers who could be identified, 2,829 (65%) ordered at least twice. They account for 93.5% of the revenue from identified customers. Many of them are probably shops or resellers restocking.

## How the data was cleaned

The raw data was left untouched and all the work was done on copies.

- Removed 5,268 exact duplicate rows.
- Filled in 1,454 missing product descriptions using other rows with the same stock code.
- Removed 2,512 rows with a unit price of zero. These are stock adjustments or free items, not sales.
- Removed non-product codes such as postage, bank charges, manual entries and gift vouchers.
- Set cancellations aside, then added them back as negative sales, so every figure is net of returns.
- Kept the rows with no customer ID (about a quarter of the data) for the country, product and monthly questions. They are left out of the customer question, since there is no way to tell who bought.

After cleaning, the data holds £9.76M of net revenue, 19,773 orders and 4,334 identified customers.

## Data

The data is the [Online Retail dataset](https://archive.ics.uci.edu/dataset/352/online+retail) from the UCI Machine Learning Repository (Chen, D., 2015), licensed CC BY 4.0. It has 541,909 rows of transactions from 1 December 2010 to 9 December 2011.

The raw file is not included here. It can be downloaded from the link above.

## Things to keep in mind

- The data covers about one year, so a yearly pattern cannot be confirmed. The link to Christmas rests on timing alone.
- December 2011 has only nine days of data, so its low total is not a real drop in sales.
- The customer findings cover identified customers only.
- Customers whose first order came late in the period may be counted as one-time buyers, so that group is probably a little too large.
- The price analysis only covers the 50 best sellers.
