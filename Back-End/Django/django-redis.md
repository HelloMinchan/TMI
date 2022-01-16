# django-redis

장고용 레디스 클라이언트 라이브러리

```python
CACHES = {
    "default": {
        "BACKEND": "django_redis.cache.RedisCache",
        "LOCATION": "redis://django@localhost:6379/0",
        "OPTIONS": {
            "CLIENT_CLASS": "django_redis.client.DefaultClient",
            "PASSWORD": "mysecret"
        }
    }
}
```

설정 후

```python
from django.core.cache import cache
# cache를 이용해 사용 (timeout=None 주면 TTL 없음)
cache.set(f"hello:world", {"hello": "world"}, timeout=None)
```

default serializer로 pickle 사용 => redis-commander로 확인 시 String (Binary) 형태로 저장 됨  
JSONSerializer로 변경 가능

```python
"OPTIONS": {
            "CLIENT_CLASS": "django_redis.client.DefaultClient",
            "SERIALIZER": "django_redis.serializers.json.JSONSerializer",
        }
```
