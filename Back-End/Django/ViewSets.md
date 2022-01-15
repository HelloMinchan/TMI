# ViewSets

DRF 제공하는 API 추상화 라이브러리  
라우터에 등록해 url conf를 자동으로 생성해주며 여러 종류의 타입이 있다.

- viewset  
  기본 뷰셋이다. permission_classes, authentication_classes 사용가능

- ReadOnlyModelViewSet  
  읽기 전용 API 만 추상화 되어있다. list(), retrieve()만 자동 구현됨

- ModelViewSet  
  기본적인 CRUD 관련 API들이 추상화되어 전부 자동 적용됨

  - list()
  - retrieve()
  - create()
  - update()
  - partial_update()
  - destroy()

  => swagger에 모델단위별로 API가 그룹핑 됨

- GenericViewSet  
  모델뷰셋에서 필요없는 API 적용을 제외하고 싶을때 mixin하여 커스터마이즈할 수 있는 뷰셋
