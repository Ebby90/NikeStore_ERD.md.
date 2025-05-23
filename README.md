# NikeStore_ERD.md

# Nike Shoe Store Data Flowchart

```mermaid
flowchart TD
    A[Customer] -->|Places Order| B[Sales Transaction]
    B -->|Includes| C[Product]
    C -->|Stock Checked| D[Inventory]
    D -->|Stock Updated| B
    B -->|Confirmation Sent To| A

    subgraph Product Details
        C1[Model Name]
        C2[Category]
        C3[Price]
        C4[Size]
        C5[Color]
    end
    C --> C1
    C --> C2
    C --> C3
    C --> C4
    C --> C5

    subgraph Customer Details
        A1[First Name]
        A2[Last Name]
        A3[Email]
        A4[Phone]
    end
    A --> A1
    A --> A2
    A --> A3
    A --> A4

    subgraph Sale Details
        B1[Sale Date]
        B2[Quantity]
        B3[Total Price]
    end
    B --> B1
    B --> B2
    B --> B3

    subgraph Inventory Details
        D1[Quantity in Stock]
        D2[Location]
    end
    D --> D1
    D --> D2
