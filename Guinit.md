erDiagram
    %% [사용자 중심 관계]
    users ||--o{ admin_logs : generates
    users ||--o{ ban_records : target
    users ||--o{ warnings : receives
    users ||--o{ vacations : requests
    users ||--o{ transactions : performs
    users ||--o{ inventory : owns

    %% [아이템 및 상점 시스템]
    items ||--o{ inventory : stored_in
    items ||--o{ transactions : involved_in

    %% [이벤트 및 콘텐츠 시스템]
    story_events ||--o{ story_posts : contains

    %% [엔티티 정의]
    users {
        string user_id PK
        string username
        string role "Admin/User 구분"
    }

    admin_logs {
        int log_id PK
        string admin_id FK
        string action
        datetime created_at
    }

    ban_records {
        int ban_id PK
        string user_id FK
        string reason
        datetime expiry_date
    }

    warnings {
        int warning_id PK
        string user_id FK
        int count
        string reason
    }

    inventory {
        int inv_id PK
        string user_id FK
        string item_id FK
        int quantity
    }

    items {
        string item_id PK
        string name
        int price
    }

    transactions {
        int tx_id PK
        string user_id FK
        string item_id FK
        int amount
        datetime tx_date
    }

    vacations {
        int vac_id PK
        string user_id FK
        date start_date
        date end_date
    }

    story_events {
        int event_id PK
        string title
    }

    story_posts {
        int post_id PK
        int event_id FK
        string content
    }

    calendar_events {
        int cal_id PK
        string title
        datetime event_date
    }

    scheduled_announcements {
        int ann_id PK
        string title
        datetime scheduled_at
    }
