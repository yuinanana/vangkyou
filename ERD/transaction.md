erDiagram
    users ||--o{ transactions : "performs (재화 주체)"
    items ||--o{ transactions : "involved_in (구매 대상)"
    oauth_admins ||--o{ transactions : "processed_by (수동 지급/회수)"

    transactions {
        int id PK "고유 ID (자동 생성)"
        string user_id FK "마스토돈 유저 ID"
        int item_id FK "아이템 ID (상점 거래 시)"
        string transaction_type "거래 유형 (구매, 보상, 환불)"
        int amount "거래 금액 (양수: 입금 / 음수: 출금)"
        string category "거래 카테고리 (상점, 이벤트, 퀘스트)"
        string status_id "연관 마스토돈 포스트 ID"
        string admin_name "처리 관리자 이름"
        string description "거래 사유 상세 설명"
        datetime timestamp "거래 발생 일시"
    }