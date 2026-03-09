The Northwind database models a fictitious company that imports and exports specialty foods from around the world. It contains a variety of tables representing business entities.

📘 Glossary of Key Terms / Tables

| Term/Table      | Description                                                                 |
|-----------------|-----------------------------------------------------------------------------|
| customers       | Businesses that place orders. Includes company name, contact info, country, etc. |
| orders          | Transactions placed by customers. Contains order date, ship date, customer ID, employee ID, etc. |
| order_details   | Line items in an order. Connects orders and products. Contains quantity, price, discount, etc. |
| employees       | Sales representatives and staff. Includes name, title, hire date, reports to, etc. |
| territories     | Geographical sales areas tied to employees.                                |
| region          | Larger geographical groupings of territories.                              |
| products        | Items for sale. Includes product name, supplier, category, price, etc.     |
| suppliers       | Companies that provide products. Includes name, contact info, country, etc. |
| shippers        | Companies used to ship products. Also known as carriers.                   |
| categories      | Product categories like Beverages, Confections, etc.                       |

See [data_tops](/northwind/data_tops) for more details.

🤔 Not sure what to ask? Here are a few sample questions.

### about employees
```
@snowy, Best Employee By Sales
```
```
@snowy, Best Employee By Sales in March 1998
```
```
@snowy, Which employees report to “Andrew Fuller”?
```
```
@snowy, List Employees and the Number of Orders They Handled (incl not active yet)
```
```
@snowy, Who is the top-selling employee by revenue?
```
### about orders
```
@snowy, List Total Orders Per Country
```
```
@snowy, List 5 top countries with max Orders in the first quarter of 1998
```
```
@snowy, List orders that took more than 30 days to ship.
```

### about products
```
@snowy, What are Top 5 best‑selling products by units sold
```
```
@snowy, List products above average price
```
```
@snowy, List Products That Have Never Been Ordered
```

### about customers and their orders
```
@snowy, List Countries with customers but without orders
```
```
@snowy, List top 5 customers by total order value.
```
```
@snowy, Which products have been ordered by customers in France, but not in Germany?
```
