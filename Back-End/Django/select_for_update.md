# select_for_update

Django ORM에서 update lock 트랜잭션을 거는법

```python
Model.objects.using("master").select_for_update().get(pk=1)
```
