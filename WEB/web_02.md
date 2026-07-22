## WEB

## 웹 서비스 흐름

## 1. 사용자 요청
- 사용자가 브라우저/앱에 URL을 입력하면, DNS 서버를 통해 해당 도메인의 실제 IP 주소를 조회함
- 브라우저/앱이 조회한 IP 주소의 웹 서버로 HTTP/HTTPS 요청을 전송

---

## 2. 서버 처리

### 1) Web Server (Apache, Nginx .. )
- HTML, Image, CSS, JavaScript 등 정적 파일을 클라이언트에 반환
- 동적 로직 처리가 필요한 요청은 뒤단의 WAS(Web Application Server)로 전달

### 2) WAS (Spring Boot, Tomcat, Jeus .. )
- JSP, Servlet, 비즈니스 로직 등 동적 데이터 생성
- __Controller__ ➔ __Service__ ➔ __Repository__ 흐름으로 요청 처리
- __JDBC (Java Database Connectivity)__: 자바 프로그램이 DB와 연결되어 데이터를 주고받을 수 있게 해줌
- __JDBC Driver__: 자바의 표준 JDBC를 __각 DB 제품(MySQL, Oracle 등)__ 에 맞게 실제 동작하도록 구현한 전용 연결 드라이버
- __ORM (Object Relational Mapping)__: JDBC 사용을 간편하게 해주는 도구 (ex: JPA, MyBatis)

- __Web Server vs WAS__  
__Web Server__: 정적 리소스 관리   
__WAS__: 동적 리소스 관리, 일반적으로 Web Server 기능을 포함

### 3) Database 
- 실제 데이터가 저장되는 물리적 공간
- __DBMS (Database Management System)__: MySQL, Oracle 등 데이터베이스를 관리하는 시스템
- ORM/JDBC를 통해 전달받은 SQL을 실행하고 그 결과를 WAS로 반환

---

## 3. 클라이언트 처리 
- 브라우저/앱이 WAS 또는 Web Server로부터 응답을 전달
- 응답받은 리소스를 브라우저 화면에 최종 표시(Rendering)
