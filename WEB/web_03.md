## WEB

## HTTP 요청
- header + body로 구성

- ### HTTP 요청 방식
    사용자가 서버에 요청할 수 있는 방식

    - __GET__: 데이터 조회 (read)   
    ex) `GET/users/1`
    - __POST__: 데이터 생성 (create)  
    ex) `POST/users`
    - __PUT__: 전체 데이터 수정 (update)  
    ex) `PUT/users/1`
    - __PATCH__: 일부 데이터 수정 (update)  
    ex) `PATCH/users/1`
    - __DELETE__: 데이터 삭제 (delete)  
    ex) `DELETE/users/1`

- ### 헤더
    메타 정보를 담는 영역

    - `content-type`: 요청 본문 타입 (ex: `application/json`)
    - `authorization`: 인증 토큰
    - `accept`: 클라이언트가 받을 수 있는 응답 형식

- ### 요청 URL 설계 규칙
    - 리소스를 명사형 복수로 표현 (ex: `/users`)
    - 계층 구조 반영 (ex: `users/{userId}/posts/{postId}`)
    - 동사는 URL이 아니라 HTTP method로 구분됨

- ### 요청 본문 (Body)
    주로 JSON 형식을 사용

    ```json
    {
        "username" : "onejong",
        "email" : "wonjonghyeon5646@naver.com",
        "password" : "1234"
    }

---
## 통신 규칙 (프로토콜)
- ### __HTTP (hypertext transfer protocol)__
    - web에서 클라이언트, 서버 간 통신 규칙
    - request - response 구조로 동작
    - 데이터가 암호화되지 않으므로 보안이 취약

- ### __HTTPS (hypertext transfer protocol secure)__
    - HTTP에 보안(SSL/TLS)를 추가한 프로토콜
    - 데이터가 암호화되어 안전하게 전달됨

---
## HTTP 응답

- ### 응답 상태 코드(status code, body)
    - __2xx: 성공__(200: 정상 처리, 201: 생성 완료, 204: 성공했지만 본문 없음)
    - __3xx: 리다이렉션__
    - __4xx: 사용자 오류__(400: 요청 오류, 401: 인증 실패, 403: 권한 없음, 404: 리소스 없음)
    - __5xx: 서버 오류__(500: 서버 오류)

- ### 응답 헤더
    - `content-type`: 응답 데이터 형식
    - `cache-control`: 캐싱 정책
    - `set-cookie`: 세션/쿠키 설정

---
성공 응답 예시 (SPA 기준)  
```json
{
    "status" : "success",
    "data" : {
        "id" : 1,
        "username" : "testuser"
    }
}
```

오류 응답 예시
```json
{
    "status" : "error",
    "message" : "Invalid email format",
    "code" : 400
}
```