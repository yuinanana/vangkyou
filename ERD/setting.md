erDiagram
    oauth_admins ||--o{ settings : "updates"

    settings {
        string key PK "설정 고유 키 (Primary Key)"
        string value "설정 값"
        string description "설정에 대한 설명 (Optional)"
        datetime updated_at "마지막 업데이트 시각"
        string updated_by FK "수정한 관리자 (oauth_admins 참조)"
    }