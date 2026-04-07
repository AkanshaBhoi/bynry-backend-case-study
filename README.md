Bynry Backend Case Study - StockFlow

Candidate Details
Name: Akansha More  
Email: akanshabhoi3@gmail.com  

---
 Overview
This repository contains my solution for the Backend Engineering Intern case study.

The system simulates a B2B Inventory Management platform where companies manage:
- Products
- Warehouses
- Inventory
- Suppliers

---

Part 1: Code Review & Debugging

### Issues Identified:
- Multiple database commits (no transaction safety)
- No input validation
- No error handling
- SKU uniqueness not enforced
- No warehouse validation
- Duplicate inventory possibility
- Price precision issues

Fixes Implemented:
- Used single transaction
- Added input validation
- Implemented try-catch error handling
- Enforced unique constraints
- Validated warehouse existence

---

 Part 2: Database Design

Tables:
- Company
- Warehouse
- Product
- Inventory
- Inventory_Log
- Supplier
- Product_Supplier
- Bundle_Items

Key Features:
- Multi-warehouse support
- Inventory tracking with logs
- Many-to-many supplier mapping
- Bundle product support

 Assumptions:
- SKU is globally unique
- Recent sales = last 30 days
- Threshold depends on product type

Questions Identified:
- What defines "recent sales"?
- Can products have multiple suppliers?
- Do we track warehouse transfers?

---

 Part 3: Low Stock Alerts API

Endpoint:
GET /api/companies/{company_id}/alerts/low-stock

Features:
- Detects low stock items
- Filters based on recent sales
- Supports multiple warehouses
- Includes supplier details
- Calculates stockout days

Edge Cases Handled:
- No recent sales
- Supplier not available
- Zero or negative stock
- Division by zero avoided
- No warehouses → empty response

📄 Submission
The complete detailed solution is available in the attached PDF file.

 Tech Stack
- Java (Spring Boot) / (as per your code)
- SQL (Database Design)

 Notes
This solution focuses on:
- Clean backend design
- Real-world business logic
- Scalability and maintainability
