# Django ORM

- ### select_for_update

```python
Model.objects.using("master").select_for_update().get(pk=1)
```
