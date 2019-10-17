Backup pg
=========

Роль для резервирования базы данных postgresql

Variables
--------------
```yaml
# backup name postfix
dump_name: $(date '+%A')_dump
# databases to dump
dump_db: []
dump_db_host: ""
dump_db_user: postgres 
dump_db_pwd: ""
dump_exclude_schemas: []
dump_exclude_tables: []
# Vacuum and reindex
dump_reindex: yes
# Cron time
dump_hour: 0
dump_minute: 30
dump_file_name: /var/dumpdb
# Extra script
dump_extra_script: ""
# Curl attempt number
dump_attempt: 5
dump_attempt_interval: 5  # in seconds
```

Example Playbook
----------------

    - hosts: dbservers
      roles:
        - role: CourseOrchestra.backup_pg
          dump_reindex: yes
          dump_db: ["{{ db_user }}"]
