# Oracleの便利なSQL

## テーブルのDDL文の抽出方法

```sql
SET SERVEROUTPUT ON;
SET FEEDBACK OFF;
SET LINESIZE 10000;
SET HANDING OFF;
SELECT dbms_metadata.get_ddl('TABLE', '<テーブル名>') FROM dual;
```

## 全テーブルのレコード数を取得する方法

```sql
SELECT
   table_name,
   to_number(
     extractvalue(
       xmltype(
    dbms_xmlgen.getxml('select count(*) c from ' || table_name))
       ,'/ROWSET/ROW/C')) count
 FROM user_tables
 WHERE TABLE_NAME NOT LIKE 'BIN$%'
   and (iot_type != 'IOT_OVERFLOW' or iot_type is null)
ORDER BY table_name;
```
