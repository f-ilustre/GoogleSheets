## Inventory Allocation System

These Google Sheets make up the Inventory Allocation System. 

1. [PASOAD](https://docs.google.com/spreadsheets/d/1lr6g3GxoQKVzvkZ5stlOkP90ldhcAZAUpf-zH6ajUgE/edit?usp=sharing)
2. [Sales Team # 1 Dashboard](https://docs.google.com/spreadsheets/d/1enfn8Z5QinpyebO96jUuJqJwW7d67g0WmXwpIUjOyTc/)
3. [Sales Team # 2 Dashboard](https://docs.google.com/spreadsheets/d/1Ryq6jHlURdSkC3gIGYeRwMG_pCYokumfkAgJiYWLXFQ/)
4. [Sales Team # 3 Dashboard](https://docs.google.com/spreadsheets/d/1OdN0FFCwOahDBTy7e9qXOS63FWoVT0BBHWd8PoeVKS0/edit?usp=sharing)

**Note**: Numbers, customer names & supplier names have been randomized. 

### Prerequisites

This Inventory Allocation System works with QuickBooks Desktop Enterprise Accountant Edition.
This version of QuickBooks cannot allocate inventory to teams or individuals.
The workaround is to upload data from QuickBooks unto the Google Sheets.
Distribution of inventory is requested through Slack. 

## PASOAD

PASOAD is an arbitrary name for the main sheet where QuickBooks data will be uploaded, preferrably by only one authorized personnel. 

**Note**: This sheet reads from multiple inventory locations (tabs 'CTL Stock', 'WCL's Stocks', 'CTL2' & 'VFL2') also monitored using Google Sheets by the Warehouse Department at the time of this sheet's creation.
For a more consolidated version of monitoring inventory from multiple locations, please see my other repository [Inventory Management Sheet](https://github.com/f-ilustre/Inventory-Management-Sheet)

Tabs | Description
---- | -----------
Subconscious 1 | Calculates the total inventory of sales teams under a particular category of customers. This is for high level decisions of the Sales Manager.
Subconscious 2 | Calculates the total quantity of an SKU on all warehouses, the total quantity allocated to the entire sales team, the total committed quantity from Sales Orders, and the remaining total quantity of SKU not allocated to anyone.
Subconscious 3 | This is the allocation per team. Received products in the warehouse are manually encoded here by the authorized personnel.
Team Paella | Sales Team # 3 is broken down further into individual allocations due to the category of their customers.
SO-2 | Sales Orders from QuickBooks are uploaded here. These are orders that have not yet been deducted from the inventory. 
CTL Stock, WCL's Stocks, CTL2, VFL2 | These tabs import data from external Google Sheets managed by the Warehouse Department.
COG | This imports data from an external Google Sheet that calculates the cost of goods per SKU INSERT GITHUB LINK HERE

**Points for Improvement**
1. The Warehouse Department deducts quantities from sales orders once invoiced. There should be an agreement on the time when these are encoded because there is a chance that the order's quantity will be deducted twice: one from deducting the quantity from Warehouse Department's inventory sheets, and the second from the committed sales order.
2. Sales Orders from QuickBooks are uploaded manually. Maybe it is possible to automate this using a Python script.
3. There is nothing stopping sales teams from overselling. There will come a point when the SKU's quantity reaches negative. In this case, the negative quantity should be adjusted to zero if there are unallocated quantities available. Otherwise, it should be deducted from other sales teams.

## Sales Team #1, #2, and #3

There are tabs titled 'Inventory' in sheets 'Sales Team # 1' and 'Sales Team # 2' that display the remaining inventory for each sales team. A similar report exists in the sheet 'Sales Team # 3' titled 'Individual Allocations'. These import data calculated by the PASOAD sheet.




