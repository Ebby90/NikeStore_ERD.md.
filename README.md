# NikeStore_ERD.md

# Nike Shoe Store ERD

```mermaid
erDiagram

    CUSTOMERS ||--o{ SALES : places
    PRODUCTS ||--o{ SALES : includes
    PRODUCTS ||--|| INVENTORY : is_stocked_in

    CUSTOMERS {
        int customer_id PK
        first_name
        last_name
        email
        phone
    }

    PRODUCTS {
        int product_id PK
        model_name
        category
        dollar price
        shoe size
        color of shoe
    }

    SALES {
        int sale_id PK
        int customer_id FK
        int product_id FK
        datetime
        sale_date
        int quantity
        dollar total_price
    }

    INVENTORY {
        int product_id PK, FK
        int quantity_in_stock
        location
    }
