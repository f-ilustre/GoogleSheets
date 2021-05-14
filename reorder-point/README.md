## Re-order Point

The [Re-order Point dashboard](https://docs.google.com/spreadsheets/d/1F5mRFa_KrtTKspz8C91P-8XVfEkw5SpNnyp6DnTt5Vc/edit?usp=sharing) was made for the Purchasing Department to help decide when to buy additional inventory.

**Note**: Numbers, customer names & supplier names have been randomized. 

### Prerequisites

The re-order dashboard works with the [PASOAD](https://docs.google.com/spreadsheets/d/1lr6g3GxoQKVzvkZ5stlOkP90ldhcAZAUpf-zH6ajUgE/edit?usp=sharing) dashboard (see [Inventory Allocation System](https://github.com/f-ilustre/inventory-allocation-system/)) to pull available inventory data. The re-order dashboard is also connected to a private sheet by the Purchasing Department where they calculate the Days Stock Level and Max Stock Level for every product category.

### Re-Order Tab

This is the main tab used by the Purchasing Department to decide if they already need to purchase additional inventory and how much.

Columns | Description
------- | -----------
Assigned Purchaser | Displays the name of the purchaser assigned to a particular product category
Category and Sub-Category | Although product categories are the ones set with a re-order point, it's also important to check the inventory of the sub-category because brands have different qualities
Re-Order Point | The inventory threshold of the category calculated by Max Stock Level divided by 2
Stock Today | Gets the total available inventory of Sales Team #1 and Sales Team #2 and adds back the inventory committed from sales orders dated greater than today()
Stock in 1 Week | Deducts commited inventory from sales orders for the next 7 days from Stock Today
Stock in 1 Month (hidden; not used) | Deducts commited inventory from sales orders for the next 30 days from Stock Today
Free Trade | Displays the inventory quantity that are not currently assigned to sales teams
Days Stock Level | Pulls data from a private sheet by the Purchasing Department
Max Stock Level | Pulls data from a private sheet by the Purchasing Department
To buy | For every category, this calculates the minimum quantity to buy in order to bring back the stock to safe levels
30-Day Average Selling Price | Displays the 30-day average selling price of a sub-category for reference
Biggest Order Past 30 Days | Gets the biggest order for a product category for the past 30 days

