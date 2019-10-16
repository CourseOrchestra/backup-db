Backup pg
=========

Роль для резервирования базы данных postgresql

Defaults
--------------
# backup name postfix
dump_name: $(date '+%A')_dump
# databases to dump
dump_db: []
dump_db_host: ""
dump_db_user: postgres 
dump_db_pwd: ""
# Исключить из резервирования
dump_exclude_schemas: []
dump_exclude_tables: []
# Vacuum and reindex
dump_reindex: yes
# Время запуска скрипта
dump_hour: 0 - 
dump_minute: 30

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: dbservers
      roles:
        - role: CourseOrchestra.backup_pg
          dump_reindex: yes
          dump_db: ["{{ db_user }}"]
