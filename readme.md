# Inventory Management System

## Overview

The Inventory Management System is a Node.js application designed to efficiently manage inventory items and suppliers. It provides CRUD operations for inventory items and suppliers, along with bulk CSV import/export functionality and low-stock alert mechanisms.

---

## Vercel Deployment Url

https://inventory-management-system-tawny.vercel.app/

## Features

1. **Inventory Management:**

   - Add, update, delete, and fetch inventory items.
   - Track inventory stock levels and automatically update stock status.

2. **Supplier Management:**

   - Manage supplier details.
   - Link inventory items to suppliers.

3. **CSV Import/Export:**

   - Import bulk inventory data using CSV files.
   - Export inventory data to CSV format for reporting or backup.

4. **Low Stock Alerts:**
   - Automatically update the stock status based on the quantity.
   - Mark items as "low stock" or "out of stock" when below the threshold.

---

## Routes

### **Item Routes** (`/items`)

| HTTP Method | Endpoint        | Description                               |
| ----------- | --------------- | ----------------------------------------- |
| `GET`       | `/allitems`     | Fetch all items with supplier details.    |
| `GET`       | `/item/:id`     | Fetch a single item by ID.                |
| `GET`       | `/exportitems`  | Export all inventory items to CSV.        |
| `GET`       | `/supplier/:id` | Fetch all items from a specific supplier. |
| `POST`      | `/additem`      | Add a new inventory item.                 |
| `POST`      | `/importitems`  | Import bulk items via a CSV file.         |
| `PATCH`     | `/update/:id`   | Update an existing item by ID.            |
| `DELETE`    | `/delete/:id`   | Delete an item by ID.                     |

### **Supplier Routes** (`/suppliers`)

| HTTP Method | Endpoint        | Description                        |
| ----------- | --------------- | ---------------------------------- |
| `GET`       | `/all`          | Fetch all suppliers.               |
| `GET`       | `/supplier/:id` | Fetch a single supplier by ID.     |
| `POST`      | `/add`          | Add a new supplier.                |
| `PATCH`     | `/update/:id`   | Update an existing supplier by ID. |
| `DELETE`    | `/delete/:id`   | Delete a supplier by ID.           |

---

## Setup and Installation

### Prerequisites:

- Node.js
- MongoDB

### Steps:

1. Clone the repository:
   ```bash
   git clone <repository-url>
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Create a `.env` file and add your MongoDB connection string:
   ```plaintext
   MONGO_URI=mongodb://localhost:27017/inventoryDB
   PORT=3000
   ```
4. Start the server:
   ```bash
   npm start
   ```

---

## Testing CSV Import/Export

### Sample CSV Format:

| title  | price  | quantity | lowStockThreshold | description   | category   | stockStatus | supplier                 |
| ------ | ------ | -------- | ----------------- | ------------- | ---------- | ----------- | ------------------------ |
| Item A | 150.00 | 5        | 10                | Sample item A | Category 1 | low stock   | 674e1d211149f878612ad191 |
| Item B | 250.50 | 20       | 10                | Sample item B | Category 2 | In Stock    | 674e1d371149f878612ad193 |
| Item C | 99.99  | 8        | 10                | Sample item C | Category 3 | low stock   | 674e1d4a1149f878612ad195 |

1. Use the `/items/importitems` endpoint to import items in bulk.
2. Use the `/items/exportitems` endpoint to download all items as a CSV file.

---

## Dependencies

- `express`: For creating the server and routes.
- `mongoose`: For MongoDB integration.
- `multer`: For handling file uploads.
- `json2csv`: For exporting data as CSV.

---
