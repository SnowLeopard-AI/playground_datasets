# Northwind Dataset Tops

This directory contains 100 rows of each table in the [Northwind](https://github.com/pthom/northwind_psql) dataset to give users a sense of the schema and data in the dataset, so they can _chat with the data more effectively_ in the [Snow Leopard playground](https://try.snowleopard.ai).

More information about the dataset can be found in the [main Northwind README](/northwind).

## Northwind Dataset Schemas

### 📦  [categories](/northwind/data_tops/categories.tsv)

- information about product categories, including their names, descriptions, and associated pictures.

| Field         | Type        | Description                                                 |
|---------------|-------------|-------------------------------------------------------------|
| category_id   | SMALLINT    | Unique identifier for each category. Primary Key.          |
| category_name | VARCHAR(15) | Name of the category. Example: 'Beverages', 'Condiments'.  |
| description   | TEXT        | Detailed description of the category.                      |

- NOTE: Snow Leopard has modified this table from the publicly available version to omit the `picture` binary blob column.

### 🤝 [customer_customer_demo](/northwind/data_tops/customer_customer_demo.tsv)

- links customers to their demographics (many-to-many relationship).

| Field            | Type         | Description                                                    |
|------------------|--------------|----------------------------------------------------------------|
| customer_id      | VARCHAR(5)   | Customer ID. Foreign Key referencing `customers(customer_id)`. |
| customer_type_id | VARCHAR(5)   | Customer type ID. FK to `customer_demographics(customer_type_id)`. |

### 👥  [customer_demographics](/northwind/data_tops/customer_demographics.tsv)

- demographic information about customer types.

| Field            | Type       | Description                                             |
|------------------|------------|---------------------------------------------------------|
| customer_type_id | VARCHAR(5) | Unique identifier for each customer type. Primary Key. |
| customer_desc    | TEXT       | Description of the customer type. Example: 'Retail', 'Wholesale'. |

### 🧾 [customers](/northwind/data_tops/customers.tsv)

- information about customers, including their contact details and addresses.

| Field         | Type         | Description                                          |
|---------------|--------------|------------------------------------------------------|
| customer_id   | VARCHAR(5)   | Unique identifier for each customer. Primary Key.   |
| company_name  | VARCHAR(40)  | Name of the customer's company.                     |
| contact_name  | VARCHAR(30)  | Name of the primary contact person.                 |
| contact_title | VARCHAR(30)  | Title of the primary contact person.                |
| address       | VARCHAR(60)  | Street address of the customer.                     |
| city          | VARCHAR(15)  | City where the customer is located.                 |
| region        | VARCHAR(15)  | Region or state where the customer is located.      |
| postal_code   | VARCHAR(10)  | Postal code of the customer's address.              |
| country       | VARCHAR(15)  | Country where the customer is located.              |
| phone         | VARCHAR(24)  | Primary phone number of the customer.               |
| fax           | VARCHAR(24)  | Fax number of the customer.                         |

### 🗺️ [employee_territories](/northwind/data_tops/employee_territories.tsv)

- associates employees with territories (many-to-many relationship).

| Field        | Type          | Description                                                   |
|--------------|---------------|---------------------------------------------------------------|
| employee_id  | SMALLINT      | Employee ID. FK to `employees(employee_id)`.                 |
| territory_id | VARCHAR(20)   | Territory ID. FK to `territories(territory_id)`.            |

### 👩‍💼 [employees](/northwind/data_tops/employees.tsv)

- information about employees, including their personal details, job titles, and reporting hierarchy.

| Field              | Type         | Description                                                         |
|--------------------|--------------|---------------------------------------------------------------------|
| employee_id        | SMALLINT     | Unique identifier for each employee. Primary Key.                  |
| last_name          | VARCHAR(20)  | Last name of the employee.                                         |
| first_name         | VARCHAR(10)  | First name of the employee.                                        |
| title              | VARCHAR(30)  | Job title of the employee.                                         |
| title_of_courtesy  | VARCHAR(25)  | Courtesy title (e.g., 'Mr.', 'Ms.', 'Dr.').                        |
| birth_date         | DATE         | Birth date of the employee.                                        |
| hire_date          | DATE         | Date the employee was hired.                                       |
| address            | VARCHAR(60)  | Street address of the employee.                                    |
| city               | VARCHAR(15)  | City where the employee resides.                                   |
| region             | VARCHAR(15)  | Region or state where the employee resides.                        |
| postal_code        | VARCHAR(10)  | Postal code of the employee's address.                             |
| country            | VARCHAR(15)  | Country where the employee resides.                                |
| home_phone         | VARCHAR(24)  | Home phone number of the employee.                                 |
| extension          | VARCHAR(4)   | Phone extension for the employee.                                  |
| notes              | TEXT         | Additional notes about the employee.                               |
| reports_to         | SMALLINT     | ID of the manager the employee reports to. FK to employees table. |
| photo_path         | VARCHAR(255) | Path to the employee's photo file.                                 |

- NOTE: Snow Leopard has modified this table from the publicly available version to omit the `photo` binary blob column.

### 📦 [order_details](/northwind/data_tops/order_details.tsv)

- line items within an order, linking products and orders.

| Field       | Type      | Description                                                       |
|-------------|-----------|-------------------------------------------------------------------|
| order_id    | SMALLINT  | Order ID. FK to `orders(order_id)`.                               |
| product_id  | SMALLINT  | Product ID. FK to `products(product_id)`.                         |
| unit_price  | REAL      | Price per unit of the product at the time of the order.           |
| quantity    | SMALLINT  | Quantity of the product ordered.                                  |
| discount    | REAL      | Discount applied to the product in this order line (0 to 1).      |

### 📑 [orders](/northwind/data_tops/orders.tsv)

- customer orders and shipping information.

| Field            | Type            | Description                                                        |
|------------------|------------------|--------------------------------------------------------------------|
| order_id         | SMALLINT         | Unique identifier for the order. Primary Key.                      |
| customer_id      | VARCHAR(5)       | Customer who placed the order. FK to `customers(customer_id)`.    |
| employee_id      | SMALLINT         | Employee who handled the order. FK to `employees(employee_id)`.   |
| order_date       | DATE             | Date the order was placed.                                         |
| required_date    | DATE             | Date the order is required to be delivered.                        |
| shipped_date     | DATE             | Date the order was shipped.                                        |
| ship_via         | SMALLINT         | Shipping method. FK to `shippers(shipper_id)`.                     |
| freight          | REAL             | Freight cost.                                                      |
| ship_name        | VARCHAR(40)      | Name of the recipient or shipping contact.                         |
| ship_address     | VARCHAR(60)      | Shipping street address.                                           |
| ship_city        | VARCHAR(15)      | City where the order is shipped.                                   |
| ship_region      | VARCHAR(15)      | Region/state where the order is shipped.                           |
| ship_postal_code | VARCHAR(10)      | Postal code for the shipping address.                              |
| ship_country     | VARCHAR(15)      | Country where the order is shipped.                                |

### 🛒 [products](/northwind/data_tops/products.tsv)

- details of items available for sale.

| Field             | Type           | Description                                                        |
|-------------------|----------------|--------------------------------------------------------------------|
| product_id        | SMALLINT       | Unique identifier for the product. Primary Key.                   |
| product_name      | VARCHAR(40)    | Name of the product.                                              |
| supplier_id       | SMALLINT       | FK to `suppliers(supplier_id)`.                                   |
| category_id       | SMALLINT       | FK to `categories(category_id)`.                                   |
| quantity_per_unit | VARCHAR(20)    | Packaging description (e.g., "10 boxes x 20 bags").               |
| unit_price        | REAL           | Price per unit.                                                   |
| units_in_stock    | SMALLINT       | Number of units currently in stock.                               |
| units_on_order    | SMALLINT       | Number of units currently on order.                               |
| reorder_level     | SMALLINT       | Minimum units before restocking is recommended.                   |
| discontinued      | INTEGER        | 1 if product is discontinued, 0 otherwise.                         |

### 🌍 [region](/northwind/data_tops/region.tsv)

- information about geographical regions.

| Field              | Type        | Description                                                    |
|--------------------|-------------|----------------------------------------------------------------|
| region_id          | SMALLINT    | Unique identifier for each region. Primary Key.               |
| region_description | VARCHAR(60) | Description of the region. Example: 'Western', 'Southern'. |

### 🚚 [shippers](/northwind/data_tops/shippers.tsv)

- information about shipping companies.

| Field        | Type        | Description                                           |
|--------------|-------------|-------------------------------------------------------|
| shipper_id   | SMALLINT    | Unique identifier for each shipper. Primary Key.     |
| company_name | VARCHAR(40) | Name of the shipping company.                        |
| phone        | VARCHAR(24) | Contact phone number for the shipping company.       |

### 🛠️ [suppliers](/northwind/data_tops/suppliers.tsv)

- information about suppliers, including their contact details and addresses.

| Field         | Type         | Description                                             |
|---------------|--------------|---------------------------------------------------------|
| supplier_id   | SMALLINT     | Unique identifier for each supplier. Primary Key.      |
| company_name  | VARCHAR(40)  | Name of the supplier's company.                        |
| contact_name  | VARCHAR(30)  | Name of the primary contact person.                    |
| contact_title | VARCHAR(30)  | Title of the primary contact person.                   |
| address       | VARCHAR(60)  | Street address of the supplier.                        |
| city          | VARCHAR(15)  | City where the supplier is located.                    |
| region        | VARCHAR(15)  | Region or state where the supplier is located.         |
| postal_code   | VARCHAR(10)  | Postal code of the supplier's address.                 |
| country       | VARCHAR(15)  | Country where the supplier is located.                 |
| phone         | VARCHAR(24)  | Primary phone number of the supplier.                  |
| fax           | VARCHAR(24)  | Fax number of the supplier.                            |
| homepage      | TEXT         | URL of the supplier's homepage.                        |

### 🗺️ [territories](/northwind/data_tops/territories.tsv)

- geographical sales areas tied to a region.

| Field                 | Type           | Description                                                        |
|------------------------|----------------|--------------------------------------------------------------------|
| territory_id           | VARCHAR(20)    | Unique identifier for the territory. Primary Key.                  |
| territory_description  | VARCHAR(60)    | Description of the territory (e.g., "Boston", "Findlay").       |
| region_id              | SMALLINT       | Region this territory belongs to. FK to `region(region_id)`.       |

### 🗺️ [us_states](/northwind/data_tops/us_states.tsv)

- information about US states, including their names, abbreviations, and regions.

| Field         | Type         | Description                                         |
|---------------|--------------|-----------------------------------------------------|
| state_id      | SMALLINT     | Unique identifier for each state. Primary Key.     |
| state_name    | VARCHAR(100) | Full name of the state.                            |
| state_abbr    | VARCHAR(2)   | Abbreviation of the state name. Example: 'CA', 'NY'. |
| state_region  | VARCHAR(50)  | Region of the state. Example: 'West', 'Northeast'. |
