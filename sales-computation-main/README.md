## Sales Computation Dashboards

These individual Google Sheets make up the Sales Computation Dashboards:

1. [Sales Computations](https://docs.google.com/spreadsheets/d/1YF34qijAMXYAJx_BYQdWHvhe21w4S0YE0CLhydwRJzM/edit?usp=sharing)
2. [Sales Team # 1 Dashboard](https://docs.google.com/spreadsheets/d/1enfn8Z5QinpyebO96jUuJqJwW7d67g0WmXwpIUjOyTc/)
3. [Sales Team # 2 Dashboard](https://docs.google.com/spreadsheets/d/1Ryq6jHlURdSkC3gIGYeRwMG_pCYokumfkAgJiYWLXFQ/)
4. [Sales Team # 3 Dashboard](https://docs.google.com/spreadsheets/d/1OdN0FFCwOahDBTy7e9qXOS63FWoVT0BBHWd8PoeVKS0/edit?usp=sharing)
5. [Sales Targets](https://docs.google.com/spreadsheets/d/1ttWYSI3M8E9ev93ar-pTCuhZyLlt7kO2eJGm-Z1JRxU/edit?usp=sharing)
6.  [COGS Calculator](https://docs.google.com/spreadsheets/d/1GugyjOdBF7adW6eDVM_lPSiFh2OWv534gL1TKz4lsR0/edit?usp=sharing)

**Note**: Numbers & customer names have been randomized. Date of the reports are only until May 14, 2020. 

### Prerequisites

This Inventory Allocation System works with QuickBooks Desktop Enterprise Accountant Edition.
QuickBooks Administrators weren't able to tag sales invoices to teams and so sales reports from the program are difficult to digest.
Also, sales agents will not be able to access their sales reports when they are on the field since QuickBooks is hosted on-site.
Data from QuickBooks must then be imported to the 'Sales Computations' sheet where queries and computations are automatically done before being imported by the sales teams' dashboards.

### Points for Improvement
1. Extracting data from QuickBooks then uploading it to Google Sheets might be automated using a Python script to save time.
2. Extracting the entire sales summary per customer per month from QuickBooks is very slow. This is probably caused by disk I/O issues since the QuickBooks file has grown too large for the program to handle. Extracting the entire report once and only updating the present month may work, but the company doesn't close accounting periods and corrections from previous transactions can change values of previous months. There is a service that condenses QuickBooks files that can be looked into.
3. 'Sales Computations' and 'Sales Targets' both have 'Data' tabs that require sales invoice data from QuickBooks. This can be condensed into one. 
4. 'Sales Target' sheet can further be optimize to reduce manual data entry. Ideally, the only input from the user should be the targetted collected sales of the agent for every month. The functions should be able to compute how much collected sales the agent should receive per day, excluding weekends.
5. 'COGS Calculator' sheet manually gets purchasing data from QuickBooks. Maybe this can be sped up by using a Python script.

## Sales Computations

Tabs 'Agent1' up to 'Agent18' gives a summary of each agent's customers and the following columns:

Column | Description
------ | -----------
Max/Month | The maximum sales generated from the customer in the history of the QuickBooks Data
Target | The target sales for the customer as set by the Sales Manager. This can be set in the 'Target-Quota Master List' tab.
Quota | The minimum sales for the customer as set by the Sales Manager. This can be set in the 'Target-Quota Master List' tab.
Past Month | Displays the sales from the customer for the previous month.
Past 30 days | Displays the sales for the past 30 days
Month to Date | Displays the sales from the beginning of the month until the present day. Note: This has been changed to 01-May to 15-May to properly label the reflected values.
Balance | Displays the total open balance of the customer.
Terms | Displays the terms of the customer.
'>15 Days Aging' | Sums the amount of open balances that have been aging for more than 15 days.
Rep Check | Displays the rep code associated with the customer.
Sales 2 Months Ago | Displays the total sales for the customer 2 months prior.
Attrite? | Displays the word 'Attrite' if the sales a month ago is less than or equal to 70% of the sales 2 months ago. 

The following tabs get their data from QuickBooks:

Tab | Description
--- | -----------
Data | Columns A:I are populated with invoice data from QuickBooks.
Aging | A summary of the open invoices from QuickBooks are uploaded here.
Customer List | The entire customer list from QuickBooks is uploaded here.
New Sales Summary | A summary of the current month's sales per customer from QuickBooks is uploaded here.
Sales Summary | The history of the company's sales per customer per month is uploaded here from QuickBooks.

## Sales Team #1, #2, and #3

This is the dashboard viewed by the agents. These sheets import agent's sales data from the 'Sales Computations' sheet.

## COGS Calculator

As QuickBooks does not have a function to calculate the cost of goods per SKU, data from purchases (bill type) are manually uploaded into this sheet. The costing method of FIFO is also impossible because the Warehouse Department was unable to follow this method logistically. As such these are the costing methods available for the sales teams depending on their preference:

Costing Method | Description
-------------- | -----------
Latest Price | This gets the maximum date of the SKU and gets the price from the bill.
30-day WA | Computes the weighted average price for the past 30 days
60-day WA | Computes the weighted average price for the past 60 days
Price to Use | Decides the price to use. The equation will first choose '30-day-WA' if its value is nonzero. If its value is zero, it checks if the value of '60-day-WA' is nonzero and chooses it if it is. If the '60-day WA' is zero, the equation will get the value from the 'Latest Price'.

Data from this sheet is imported by the dashboards of Sales Team # 1-3


