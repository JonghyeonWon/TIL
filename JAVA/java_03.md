# JAVA

## 데이터 타입의 분류
자바의 데이터 타입은 기본형과 참조형으로 나눔

- __기본형__
  - 실제 값을 저장
  - __숫자형__: 정수(`byte`, `short`, `int`, `long`), 실수(`float`, `double`)
  - __문자형__: `char` (작은따옴표 `''` 사용)
  - __논리형__: `boolean` (`true`, `false`)

- __참조형__
  - 실제 값이 있는 메모리의 주소를 저장
  - 기본형을 제외한 모든 타입
  - ex) `String` (문자열은 기본형이 아님, 큰따옴표 `""` 사용)

---

## 변수의 구문 형식 및 선언 위치

__변수의 구문 형식__
```text
[접근지정자(생략 가능)] [변수타입] [변수명] = value;
```

__자료형 예시 코드__
```java
public class VariableApp {
    
    // 전역변수가 여기에 위치함
    public String  name       = "jhwon";    // 문자열
    public int     age        = 24;         // 정수
    public double  height     = 165.5;      // 실수
    public boolean isMarriage = false;      // 불린 타입
    public char    gender     = 'm';        // 문자
    
    // 이 클래스는 main 메서드가 없으므로 컴파일은 되지만 실행은 불가
}
```