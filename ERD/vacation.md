erDiagram
    users ||--o{ vacations : "requests"
    oauth_admins ||--o{ vacations : "approves/registers"

    vacations {
        int id PK "휴가 기록 고유 ID (Primary Key)"
        string user_id FK "휴가 대상 유저 ID (users 참조)"
        date start_date "휴가 시작 날짜"
        date end_date "휴가 종료 날짜"
        time start_time "시작 시각 (선택)"
        time end_time "종료 시각 (선택)"
        string reason "휴가 사유 (선택)"
        boolean approved "승인 여부 (기본값 True)"
        string registered_by FK "등록/승인 관리자 (oauth_admins 참조)"
        datetime created_at "기록 생성 일시"
    }