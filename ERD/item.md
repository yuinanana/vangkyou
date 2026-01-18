erDiagram
    items ||--o{ inventory : "stored_in"
    items ||--o{ transactions : "involved_in"

    items {
        int id PK "아이템 고유 ID (Primary Key)"
        string name "아이템 이름 (필수)"
        int price "가격 (필수)"
        string description "아이템 상세 설명 (Optional)"
        string category "카테고리 (Optional)"
        string image_url "아이템 아이콘/이미지 URL (Optional)"
        boolean is_active "판매 활성 여부 (기본값 True)"
        int initial_stock "초기 재고량"
        int current_stock "현재 남은 재고량"
        int sold_count "누적 판매 수량"
        boolean is_unlimited_stock "무제한 재고 여부"
        int max_purchase_per_user "유저당 최대 구매 제한 (Optional)"
        int total_sales "총 판매 금액"
        datetime created_at "아이템 등록 일시"
    }