erDiagram
    oauth_admins ||--o{ scheduled_announcements : "creates"

    scheduled_announcements {
        int id PK "고유 ID (자동 생성)"
        string post_type "공지 유형 (일반, 이벤트 등)"
        string content "공지 본문 내용"
        datetime scheduled_at "발송 예정 일시"
        string visibility "공개 범위 (public, unlisted 등)"
        boolean is_public "공개 여부"
        string status "상태 (pending, published 등)"
        string created_by FK "작성 관리자 (oauth_admins 참조)"
        string mastodon_scheduled_id "마스토돈 서버 측 예약 ID (Optional)"
        datetime created_at "데이터 생성 일시"
        datetime published_at "실제 발송 완료 일시"
    }