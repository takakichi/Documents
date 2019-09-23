# テーブル一覧の取得

```sql
SELECT * FROM sys.all_objects 
WHERE type='U' AND type_desc='USER_TABLE' and schema_id = 1
ORDER BY name
```
