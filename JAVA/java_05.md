# JAVA

## 클래스(Class)와 인스턴스(Instance)의 차이
클래스는 인스턴스 생성을 위한 템플릿일 뿐, 클래스와 인스턴스는 같은 개념이 아님

- __클래스 (Class):__ 객체를 담기 위한 그릇(템플릿)
- __인스턴스 (Instance):__ 클래스를 바탕으로 프로그램 메모리에 실제로 생성된 객체

---

## 클래스 설계 및 인스턴스 생성 예제

__Teacher.java (클래스 코드)__
```java
public class Teacher {
    // 전역 변수 (속성)
    public String  name;
    public int     age;
    public String  address;
    public boolean isMarriage;

    // 매개변수 X + 반환 값 X
    public void eating() {
        System.out.println("강의하기 위해서 밥을 먹는다.");
    }

    // 매개변수 O + 반환 값 O
    public String teaching(String subject) {
        return "강사님이 가르치는 과목은 " + subject + "입니다.";
    }
}
```
---

__TeacherApp.java (인스턴스 이용 코드)__
```java
public class TeacherApp {
    
    public static void main(String[] args) {

        // 인스턴스 생성 -> 생성된 인스턴스의 주소값을 참조 변수에 저장
        Teacher teacher = new Teacher(); 

        // 인스턴스의 변수 사용
        teacher.name = "jhwon";
        System.out.println(teacher.name);

        // 인스턴스의 메서드 호출
        teacher.eating();
        
        // 매개변수를 전달하고 반환 값을 받아와 출력
        String result = teacher.teaching("자바");
        System.out.println(result);
    }
}
```