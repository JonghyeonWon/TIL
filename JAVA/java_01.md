
## JAVA

# OOP(Object Oriented Programming)
실세계의 모든 사물이나 개념을 객체로서 다루는 프로그래밍 방법

__class__

실세계에 존재하는 오브젝트들을 프로그램 세계의 객체로 만들기 위한 템플릿

- class는 __변수__(variable), __메서드__(method)로 이루어짐
- 프로그램 영역에서 사용할 수 있는 __객체__(instance) 생성 가능

__class vs instance__


class: 실세계에 존재하는 객체  
instance: 프로그램 세계에서 존재하는 객체

# JAVA 개발 환경
__JDK__(java development kit), __JRE__(java runtime environment), __JVM__(java virtual machine)

JDK를 install 하면 JVM이 설치되고, 그 안에 JRE가 존재하는 구조

java software: os의 종류에 독립적으로, OS 위에 JVM만 존재한다면 그 안에서 java software가 동작가능

JDK를 설치하면 os 위에 JVM이 설치되고, JVM 위에는 library가 존재하여 user가 JVM에서 동작하는 application을 만들 수 있음
(java software는 JVM에는 의존적임)

oracle, adoptium, openJDK, eclipse .. : JDK 제공

__JDK-11__: 현업에서 가장 많이 release된 버전

__JDK-17, JDK-21__: spring boot와의 호환성 
