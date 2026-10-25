# Assignment 1: Short note

**a. Customer identifiers.** `customer_id` is created for every order, so each value appears on exactly one order (99,441 values for 99,441 orders). `customer_unique_id` identifies the real person and repeats when the same person orders again (96,096 distinct values, up to 17 `customer_id`s for one person). To count customers I use `count(DISTINCT customer_unique_id)`; `customer_id` is only the primary key of the table.

**b. Junction table.** `order_items` is the junction table: its composite key is (`order_id`, `order_item_id`), and with the foreign keys `order_id`, `product_id` and `seller_id` it resolves the many-to-many relationships orders ↔ products and orders ↔ sellers (and, through them, products ↔ sellers).

**c. Diagram vs. data.** The data is stricter than the diagram for products → order_items: I drew "zero or many" (a product can sit unsold in the catalogue), but the cardinality query shows every product has at least 1 item (min = 1, max = 527). The same is true for sellers → order_items (min = 1) and customers → orders (exactly 1 order each, though I drew "one or many"). The circle on orders → order_items is justified by the data: 775 orders have no items at all (mostly `unavailable` and `canceled`), so an order may have zero items.
