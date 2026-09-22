# UAT Runbook — Product-2 (Product Catalog & Inventory)

## Feature
Catalog item registration and stock level tracking

## Preconditions
- Service is configured with valid environment (`.env.local` or `.env.example`).
- Database migrations have been applied via `make migrate`.
- Required port is free and accessible.

## Steps
1. Start Product-2 service using `python app.py --serve --port 8082`
2. Create product catalog item via POST /api/v1/products with SKU, title, and price
3. Verify item retrieval via GET /api/v1/products
4. Check GET /metrics to verify domain entity count incremented

## Expected Results
- Product item created with valid SKU and price
- GET /api/v1/products returns matching SKU record
- domain_entities_total metric in /metrics reflects new item count

---
*Author: QA & Primary Owner (MasterSpec Section 31.1, Section 33.1)*
*Verification Contract: `verification/contract.yaml`*
