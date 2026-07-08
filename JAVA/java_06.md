# 프로젝트 구조

## 패키지(Package)와 의존성
- __패키지 구성__: 각 기능들을 하나의 패키지 단위로 묶어서 관리
- __의존 관계__: 패키지 내부의 클래스들은 서로 의존 관계를 생성
- __외부 참조__: 패키지 외부의 클래스나 기능이 필요할 때는 __`import`__ 키워드를 사용

---

## Spring Framework
스프링 프레임워크(Spring Framework)는 __MVC(Model-View-Controller) 패턴__ 을 기반으로 구동

- __xxxController.java__
  - 클라이언트의 요청을 받는 진입점
  - 비즈니스 로직 처리를 위해 __Service__ 에 의존함
  - 최종적으로 프론트엔드가 원하는 데이터를 __JSON 형태__ 로 변환하여 전달

```java
package test.ctrl;

import test.service.TestService;

public class TestController {

    public TestService service = new TestService();
}
```

- __xxxServiceImpl.java__
  - 핵심 비즈니스 로직을 수행하는 공간
  - 데이터 처리를 위해 __Repository에 의존__ 

```java
package test.service;

import test.repository.TestRepository;

public class TestService {

    public TestRepository repository = new TestRepository();
}
```

- __xxxRepository.java / xxxDao.java__
  - 데이터베이스(DB)와의 상호작용을 담당
  - DB에서 전달받은 데이터를 __DTO 형태로 변환__ 하여 Service에 전달
  - Repository와 DBMS 사이의 상호작용 및 매핑 작업은 __JPA__ 나 __MyBatis__  같은 프레임워크가 돕거나 처리해 줌

- __xxxDTO.java / xxxVO.java / xxxEntity.java__
  - 데이터를 주고받을 때 사용하는 데이터 객체 

---

## 소프트웨어 설계 지향점
좋은 애플리케이션 아키텍처를 위해 항상 다음 두 가지 설계 원칙을 지향해야 함

- __높은 응집도__: 하나의 패키지나 클래스는 유사한 기능 및 목적을 가진 코드끼리 끈끈하게 모여있어야함

- __낮은 결합도__: 각 레이어(Control ➔ Service ➔ Repository) 간의 불필요한 의존성을 줄여, 하나의 코드가 변경되어도 다른 코드가 망가지지 않도록 유연하게 설계해야 함

--- 

# JAVA 패키지 계층 구조 

```text
    test/                     <-- 최상위 패키지
    ├── domain/                 <-- 데이터 객체 관리
    │   ├── dto/
    │   │   └── TestRequestDTO.java
    |   |   └── TestResponseDTO.java
    │   └── entity/
    │       └── TestEntity.java
    │
    ├── controller/            <-- 클라이언트 요청 수신
    │   └── TestController.java
    │
    ├── service/               <-- 비즈니스 로직 수행
    │   ├── TestService.java
    │
    └── repository/            <-- DB 및 JPA 관리
        └── TestRepository.java