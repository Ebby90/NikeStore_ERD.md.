# NikeStore_ERD.md

# Nike Shoe Store ERD

# Nike Shoe Retail Store - ERD

This Entity-Relationship Diagram (ERD) models the database for a Nike shoe retail store. The diagram illustrates the relationships and constraints between four key entities:

- **Products**: Different models of Nike shoes sold in the store.
- **Customers**: Individuals who purchase shoes from the store.
- **Sales**: Transactions linking customers to the shoes they purchase.
- **Inventory**: Tracks stock levels for each shoe model.

```mermaid
erDiagram
    PRODUCT {
        int product_id PK
        string name
        string category
        string size
        float price
    }

    CUSTOMER {
        int customer_id PK
        string first_name
        string last_name
        string email
        string phone
    }

    SALE {
        int sale_id PK
        date sale_date
        int customer_id FK
        int product_id FK
        int quantity
        float total_price
    }

    INVENTORY {
        int inventory_id PK
        int product_id FK
        int quantity_in_stock
        string location
    }

    CUSTOMER ||--o{ SALE : places
    PRODUCT ||--o{ SALE : includes
    PRODUCT ||--|| INVENTORY : stocked_in
