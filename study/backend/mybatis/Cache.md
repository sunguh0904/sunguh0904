## MyBatis Cache
> ### `<cache>` 태그란?
`<cache>` 태그는 MyBatis에서 쿼리 결과를 캐싱하여 성능을 향상시키기 위해 사용되는 태그입니다. 주로 자주 변경되지 않는 데이터를 캐시하여 데이터베이스 호출을 줄이고 응답 시간을 단축시킵니다.

### 사용 예시
```xml
<cache/>
```

> ### `<cache-ref>` 태그란?
`<cache-ref>` 태그는 다른 매퍼의 캐시를 참조하기 위해 사용됩니다. 동일한 키를 사용하여 캐시된 데이터를 불러올 수 있습니다.

### 사용 예시
```xml
<cache-ref namespace="com.example.mapper.AnotherMapper"/>
```

> ### 왜 사용해야 하는가?
1. **성능 향상**: 쿼리 결과를 캐싱하여 데이터베이스 호출을 줄이고 응답 시간을 단축시킬 수 있음
2. **리소스 절약**: 캐싱을 통해 데이터베이스 리소스를 절약할 수 있음

> ### 쉬운 요약
1. `<cache>` 태그는 쿼리 결과를 캐싱하여 성능을 향상시키는 데 사용됨
2. `<cache-ref>` 태그는 다른 매퍼의 캐시를 참조하는 데 사용됨

> ### 비유
1. 메모리
    - `<cache>` 태그는 자주 사용하는 데이터를 메모리에 저장하는 것과 같음
    - 예: 자주 조회하는 데이터를 메모리에 저장하여 빠르게 접근

2. 책갈피
    - `<cache-ref>` 태그는 다른 책의 책갈피를 참조하는 것과 같음
    - 예: 다른 매퍼의 캐시된 데이터를 참조하여 재사용

[뒤로](MyBatis.md)
