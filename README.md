# Inventory Management System

A simple MySQL-based inventory management system to track products, suppliers, purchases, and sales, complete with automated stock adjustments via SQL triggers.

## Features

- Manage product categories, suppliers, and inventory
- Record purchases and sales
- Automatically increase stock on purchase
- Automatically decrease stock on sale (with stock validation)
- Clean and relational schema with foreign key constraints

## Database Schema

Tables:
- `categories`
- `suppliers`
- `products`
- `purchases`
- `sales`

Triggers:
- `after_purchase_insert`: Increases product stock when a purchase is recorded
- `before_sale_insert`: Decreases product stock when a sale is made, and blocks the sale if stock is insufficient

## Getting Started

### 1. Clone the repository

```bash
https://github.com/yourusername/inventory-management-system.git

2. Import the database

Use any MySQL client (e.g., MySQL Workbench or command line).

Import the schema:


mysql -u youruser -p yourdatabase < schema.sql


3. Start using the database

You can now begin adding categories, suppliers, products, and recording purchases/sales.

Example

-- Add a new product
INSERT INTO products (product_name, category_id, supplier_id, unit_price, quantity_in_stock)
VALUES ('Notebook', 1, 2, 2.99, 100);

-- Record a purchase
INSERT INTO purchases (product_id, supplier_id, quantity, purchase_price)
VALUES (1, 2, 50, 2.50);

-- Record a sale
INSERT INTO sales (product_id, quantity, sale_price)
VALUES (1, 20, 3.50);

License

This project is open-source and available under the MIT License.


---

Author: Gelmar Vallespin
GitHub: @xvalfiles
