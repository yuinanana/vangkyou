erDiagram
    oauth_admins ||--o{ story_events : "creates"
    story_events ||--o{ story_posts : "contains"

    story_events {
        int id PK "이벤트 ID (자동 생성)"
        string title "이벤트 제목"
        string description "이벤트 상세 설명 (Optional)"
        datetime start_time "첫 번째 포스트 발송 시각"
        int interval_minutes "포스트 간 발송 간격 (단위: 분)"
        string status "이벤트 전체 상태 (pending, in_progress, completed 등)"
        string created_by FK "작성 관리자 (oauth_admins 참조)"
        datetime created_at "생성 일시"
        datetime published_at "발송 시작 시각"
    }

    story_posts {
        int id PK "포스트 고유 ID"
        int event_id FK "소속 이벤트 ID (story_events 참조)"
        int sequence "발송 순서 (1, 2, 3...)"
        string content "포스트 본문 내용"
        string media_urls "첨부 미디어 URL (JSON)"
        string status "개별 포스트 발송 상태"
        string mastodon_post_id "마스토돈 발행 ID (Optional)"
        datetime scheduled_at "예약된 발송 시각"
        datetime published_at "실제 발송 완료 시각"
        string error_message "발송 실패 시 에러 내용"
    }