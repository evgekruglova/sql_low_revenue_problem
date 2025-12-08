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
