erDiagram
    users ||--o{ warnings : "receives"
    oauth_admins ||--o{ warnings : "issues (system/admin)"

    warnings {
        int id PK "경고 고유 ID (Primary Key)"
        string user_id FK "대상 유저 ID (users 참조)"
        string warning_type "경고 유형 (activity, isolation, bias, avoidance)"
        int check_period_hours "모니터링 기간 (시간 단위)"
        int required_replies "기준 답글 수"
        int actual_replies "실제 확인된 답글 수"
        string message "전송된 경고 메시지"
        boolean dm_sent "마스토돈 DM 전송 성공 여부"
        string admin_name FK "발행 주체 (system 또는 관리자명)"
        datetime timestamp "경고 발생 시각"
    }