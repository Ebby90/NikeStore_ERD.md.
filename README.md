# Nike Shoe Store ERD

PRODUCT: Each product has a unique product_id, along with attributes such as name, category, size, and price.

CUSTOMER: Each customer has a unique customer_id, and associated contact details.

SALE: Represents a sales transaction. Each record links a customer and a product, with additional details like quantity and total_price.

INVENTORY: Keeps track of how many units of each product are available and where they are stored.

Relationships:
A customer can place multiple sales (||--o{).

A product can be included in many sales (||--o{).

A product is represented in exactly one inventory record (||--||), assuming each product is uniquely identified and stored in a single location.

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
        string FirstNme
        string LastName
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
