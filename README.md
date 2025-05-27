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
        string Nme
        string Category
        string Size
        float Price
    }

    CUSTOMER {
        int customer_id PK
        string FirstNme
        string LastName
        string Email
        string Phone
    }

    SALE {
        int SaleId PK
        date SaleDate
        int CustomerId FK
        int ProductId FK
        int Quantity
        float Total_Price
    }

    INVENTORY {
        int InventoryId PK
        int ProductId FK
        int Quantity_In_Stock
        string Location
    }

    CUSTOMER ||--o{ SALE : places
    PRODUCT ||--o{ SALE : includes
    PRODUCT ||--|| INVENTORY : stocked_in
