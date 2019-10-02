# SQLServerの便利なSQL

## テーブル一覧の取得

```sql
SELECT * FROM sys.all_objects 
WHERE type='U' AND type_desc='USER_TABLE' and schema_id = 1
ORDER BY name
```

## 全テーブルのレコード数を取得する方法

```sql
SELECT obj.name AS TableName, indx.rows As RowNum
  FROM sys.objects AS obj
  JOIN sys.sysindexes AS indx
  ON obj.object_id = indx.id AND indx.indid < 2
  WHERE obj.type = 'U'
  ORDER BY obj.name
```
