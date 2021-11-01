# SELECT FOR UPDATE

`SELECT FOR UPDATE` 쿼리란 가장 먼저 LOCK을 획득한 세션의 ROW들을 UPDATE 쿼리 후 커밋되기 이전까지 다른 세션들이 변경하지 못하게 하는 기능이다. (읽기 작업은 가능함!)

```SQL
SELECT * FROM person WHERE id=1 FOR UPDATE;
```
