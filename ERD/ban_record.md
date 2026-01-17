erDiagram
    users ||--o{ ban_records : "target"

    ban_records {
        int id PK "자동 생성 고유 식별자"
        string user_id FK "아웃된 유저의 Mastodon ID"
        datetime banned_at "아웃 발생 시각"
        string banned_by "아웃 처리자 (관리자 또는 system)"
        string reason "아웃 사유"
        int warning_count "아웃 당시 누적 경고 횟수"
        string evidence_snapshot "증거 스냅샷 (Optional)"
        boolean is_active "현재 아웃 상태 여부 (True/False)"
        datetime unbanned_at "아웃 해제 시각 (Optional)"
        string unbanned_by "아웃 해제자 (Optional)"
        string unban_reason "아웃 해제 사유 (Optional)"
    }