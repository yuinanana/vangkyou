erDiagram
    users ||--o{ inventory : "owns"
    items ||--o{ inventory : "is_stored"

    inventory {
        int id PK "인벤토리 고유 ID"
        string user_id FK "보유 유저 (users 참조)"
        int item_id FK "아이템 ID (items 참조)"
        int quantity "보유 수량 (기본값 1)"
        datetime acquired_at "획득 시각 (Optional)"
    }