erDiagram
    users ||--o{ calendar_events : "created_by"

    calendar_events {
        int id PK "이벤트 ID (자동 생성)"
        string title "이벤트 제목"
        string description "이벤트 상세 설명 (Optional)"
        date event_date "이벤트 시작 날짜"
        time start_time "이벤트 시작 시각 (Optional)"
        date end_date "이벤트 종료 날짜 (Optional)"
        time end_time "이벤트 종료 시각 (Optional)"
        string event_type "이벤트 유형 (event, holiday, community 등)"
        boolean is_global_vacation "리뉴얼/전체 휴식 기간 여부"
        string created_by FK "생성 관리자 (users 참조)"
        datetime created_at "생성 일시"
        datetime updated_at "수정 일시"
    }









    