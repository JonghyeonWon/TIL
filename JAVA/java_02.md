# JAVA

## JAVA 컴파일 및 실행 원리
작성한 소스 코드가 컴퓨터에서 실행되기까지의 변환 과정

__컴파일(Compile)__
- `abc.java`(인간이 작성한 코드) -> 컴퓨터가 이해할 수 있는 형태로 변환 필요
- __컴파일러__가 이 역할을 수행하며, `bin` 폴더 내부의 __`javac`__ 명령어로 컴파일 진행
- 컴파일이 완료되면 __`abc.class`__ 파일(Byte Code)이 생성됨

__Binary Code vs Byte Code__
- __Binary Code__: OS에 종속적
- __Byte Code__: OS에 독립적이며, VM에 의존

__실행__
- 컴파일된 바이트 코드(`.class`)는 __인터프리터__ 를 통해 실행됨
- `bin` 폴더 내부의 __`java`__ 명령어로 실행 가능

--- 

## JAVA 식별자 (Identifier) 규칙
자바는 대소문자를 엄격하게 구별

- __class__
  - 첫 글자가 __대문자__ 로 시작
  - ex) `Teacher`

- __variable__
  - 첫 글자가 __소문자__ 로 시작
  - 두 번째 단어부터 대문자로 잇는 __카멜 케이스(Camel Case)__ 사용
  - ex) `englishSum`

- __method__
  - 변수와 마찬가지로 첫 글자는 __소문자__, 이후는 __카멜 케이스__ 사용
  - ex) `playGround()`

---

## JAVA 프로그램 기본 구조 (Hello World)
자바 코드의 가장 기본적인 형태와 특징

__GreetingApp.java__

```java
// 파일의 이름과 클래스 이름은 동일해야함
public class GreetingApp {

    // 실행 시작점
    // IDE에서 run을 눌러 실행 가능
    public static void main(String args[]) {
        System.out.println("처음 만나는 자바세상");
    }

}
// 파일을 저장하면 동시에 컴파일이 진행됨