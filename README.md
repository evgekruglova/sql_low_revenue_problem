# sql_low_revenue_problem

A fully SQL-based analysis to determine how to allocate the 2019 marketing budget. The project examines customer, order, and payment data to identify growth drivers and underperforming segments.

**Key Metrics** : monthly revenue, AOV, number of orders

**Stakeholder**: Marketing team

**Main Questions**: Which segments are slowing growth? How should the marketing team allocate its efforts for maximum impact?

**Segments Analyzed**:customer_state, customer_city, payment_type

**Datasets Used** (on a website app.mode.com) : 

career_nub.ecomm_customers_dataset

career_nub.ecomm_orders_dataset

career_nub.ecomm_order_payments_dataset

career_nub.ecomm_customers_dataset is joined with career_nub.ecomm_orders_dataset via customer_id in the first temporary table.
In the second temporary table, this result is joined with career_nub.ecomm_order_payments_dataset via order_id.

The file sql_ commands includes 7 steps which help us to draw insights from the results of our commands:

✅ **Step 1 — Monthly AOV (Average Order Value)**

What we do: Calculate the average order value for each month (Jan–Jun 2018) using only delivered orders.
Why: To check whether revenue drops are caused by changes in average order size.
Insight: AOV dips slightly in February and May, but overall remains stable — meaning the revenue decline is not caused by smaller order amounts.

✅ **Step 2 — Monthly Order Volume (2018)**

What we do: Count how many delivered orders were placed each month in 2018.
Why: To understand demand fluctuations and identify weak months.
Insight: Overall order volume in 2018 is much higher than in 2017, but February and June show clear drops — these months require deeper investigation.

✅**Step 3 — Monthly Revenue Approximation**

What we do: Estimate revenue per month using the formula:
AVG(payment_value) * COUNT(customer_id)
Why: To combine AOV and order volume and visualize total revenue trends.
Insight: Revenue sharply declines in February and June. These declines are driven mainly by fewer orders, not by lower AOV.

✅ **Step 4 — State-Level Decline (January vs February)**

What we do: Compare revenue per state between January and February and identify states with strong declines (>1.5×).
Why: To locate geographic segments that contribute most to the revenue drop.
Insight: States AC, AL, AP, PA, PB show significant declines. Many orders in these states contribute less than 2% of monthly revenue, indicating a long tail of very small transactions.

✅ **Step 5 — Checking Small Payments (January vs February)**

What we do: Measure what percentage each payment contributes to monthly totals, classify them as “low” (<2%) or “high,” and examine distribution.
Why: To determine whether February’s drop is caused by many low-value orders.
Insight: February contains a higher share of very small payments; combined with fewer orders overall, this explains the revenue decline.

✅ **Step 6 — Small Payments in May vs June**

What we do: Count low-value payments in May and June and compare.
Why: To see whether June’s decline is also driven by small checks.
Insight: June has more low-value transactions than May despite higher AOV — confirming that the issue is again too many small orders and fewer total orders.

✅ **Step 7 — Payment Type Distribution (February)**

What we do: Calculate the percentage of each payment type (credit card, boleto, voucher, debit card) per state.
Why: To check whether payment methods influence revenue decline.
Insight: Credit card dominates in both good and bad months; payment type structure is almost identical.
➡️ Conclusion: Payment type is not a driver of revenue decline.

🎯 **Final Conclusion Across All Steps**

Revenue declines in February and June are not caused by payment methods or average order value.
AOV remains stable, but in these two months: order volume drops significantly, 
and there is a high concentration of very small transactions, especially in states like AC and AP.

Several states and cities consistently generate low revenue, creating a long tail of micro-orders that pull monthly results down.
Payment type distribution is stable across all months, so it does not explain the decline.

📌 **Marketing Recommendations for 2019**

1. Address weak months (February & June)

- Run targeted seasonal promotions.

- Retarget January buyers for February.

- Use mid-year sales and larger basket incentives in June (free shipping threshold, bundle offers).

2. Focus on priority geographies

- Invest more in high-potential but underperforming states (PA, PB, GO, MT).

- Apply turnaround strategies in chronically weak states (AC, AP) — upsell, bundles, performance ads.

- Maintain only basic coverage in low-impact regions.

3. Reduce small-order volume

- Raise the free-shipping threshold.

- Promote larger baskets (“add X to unlock discount,” bundles, 3-for-2 offers).
