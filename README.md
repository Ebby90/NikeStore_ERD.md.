# NikeStore

erDiagram

    CUSTOMERS ||--o{ SALES : places
    PRODUCTS ||--o{ SALES : includes
    PRODUCTS ||--|| INVENTORY : stocked_in

    CUSTOMERS {
        int customer_id PK
        string first_name
        string last_name
        string email
        string phone
    }

    PRODUCTS {
        int product_id PK
        string model_name
        string category
        decimal price
        string size
        string color
    }

    SALES {
        int sale_id PK
        int customer_id FK
        int product_id FK
        datetime sale_date
        int quantity
        decimal total_price
    }

    INVENTORY {
        int product_id PK, FK
        int quantity_in_stock
        string location
    }
