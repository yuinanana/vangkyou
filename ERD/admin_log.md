erDiagram
    users ||--o{ admin_logs : "performs"

    admin_logs {
        int id PK "로그 고유 식별자"
        string admin_id FK "관리자 ID (users 테이블 참조)"
        string action_type "활동 유형 (create, update, delete 등)"
        string target_type "대상 유형 (user, item, setting 등)"
        string target_id "대상 ID (Optional)"
        string details "상세 설명 (JSON 또는 Text)"
        string ip_address "접속 IP 주소"
        datetime created_at "생성 일시"
    }
