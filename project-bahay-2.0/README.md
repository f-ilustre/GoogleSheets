## Project Bahay 2.0 Dashboards using Google Sheets

These Google Sheets read data from Shopify and automatically generate reports for various departments:

1. [Raw Data](https://docs.google.com/spreadsheets/d/1JPNHrKz08RAabST2jJa834r2NP2srz_dpj6yi6ENJrU/edit?usp=sharing)
2. [Withdrawal Requests & Picklist](https://docs.google.com/spreadsheets/d/1UIv2elTBvxq67dxqGO3cqYN5cgZyMMARZOUenQ5zkqs/edit?usp=sharing)
3. [COD List](https://docs.google.com/spreadsheets/d/1GCRXFU8dXHpsfg1wNvs6pTFTC_TMXZRggPzFM2yT8OY/edit?usp=sharing)
4. [Truck by Client](https://docs.google.com/spreadsheets/d/1fqMDx6mAihxm63ENSacxzOX3pT_3cK_EdrjlQnrX3Eg/edit?usp=sharing)
 

### Prerequisities 

The Google Sheets work with a subscription to the following:

1. Advanced Shopify 
2. Sheets - Sync with G Sheets (Addon in Shopify)

## 1. Raw Data

This Google Sheet gets its data from the the Shopify application 'Sheets - Sync with G Sheets'.
The data is updated manually by clicking a button in 'Sheets - Sync with G Sheets'.
This sheet is the source of the other Google Sheets to prevent end users from accidentally manipulating the raw data.

IMPORTANT: Some data had been randomized to protect the personal information of the customers.

## 2. Withdrawal Request & Picklist

This Google Sheet reads data from 'Raw Data' and automatically displays 2 reports:

1. The tab 'ShopifyPicklist' displays a detailed report of all open orders that needs to be fulfilled as well as lists all orders whose packing slips needed to be printed in Shopify.
2. The tab 'Withdrawal Request' displays a summary of all items that needed to be picked from the warehouse.

## 3. COD List

This Google Sheet reads data from 'Raw Data' and automatically displays a report designed for the Collections department.
Although this data can easily be accessed through Shopify, the user limitation of Shopify cannot accomodate the headcount of employees assigned to monitor Cash on Delivery orders. This sheet provides an external report to monitor the payment and fulfillment status on all Cash on Delivery orders.

## 4. Truck by Client

This Google Sheet reads data from 'Withdrawal Request & Picklist' and displays the orders that are pending for delivery including the address and zip codes. Trucks can be assigned to the orders along with the names of the employees assigned for the delivery. Once these are filled up, a driver's manifest is automatically generated which serves as the delivery route for the truck. 


