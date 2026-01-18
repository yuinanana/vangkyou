erDiagram
    oauth_admins ||--o{ admin_logs : "performs"
    oauth_admins ||--o{ calendar_events : "creates"
    oauth_admins ||--o{ items : "manages"
    oauth_admins ||--o{ ban_records : "executes"

    oauth_admins {
        int id PK "고유 식별자 (Primary Key)"
        string mastodon_acct "마스토돈 계정 주소 (Unique)"
        string display_name "표시 이름 (Optional)"
        string added_by "해당 관리자를 추가한 관리자"
        boolean is_active "계정 활성화 상태 (기본값 True)"
        datetime added_at "관리자 등록 일시"
        datetime last_login_at "최근 로그인 일시"
    }