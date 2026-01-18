erDiagram
    users ||--o{ transactions : "performs"
    users ||--o{ inventory : "owns"
    users ||--o{ ban_records : "is_targeted"
    users ||--o{ vacations : "requests"

    users {
        string mastodon_id PK "마스토돈 고유 ID (Primary Key)"
        string username "유저명 (@계정)"
        string display_name "표시 이름 (선택)"
        string role "사용자 역할 (user, admin 등)"
        string dormitory "배정 기숙사 (선택)"
        int balance "현재 잔액 (갈레온)"
        int total_earned "누적 획득 금액"
        int total_spent "누적 지출 금액"
        int reply_count "총 답글 수"
        int warning_count "누적 경고 횟수"
        boolean is_key_member "주요 멤버 여부"
        datetime last_active "마지막 활동 시각"
        datetime last_check "마지막 체크 시각"
        datetime created_at "계정 생성 시각"
        string role_name "마스토돈 역할명"
        string role_color "마스토돈 역할 색상"
    }