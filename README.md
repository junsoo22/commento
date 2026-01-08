# 1주차 과제 - 개발환경 설정

## 1. 개발환경
- JDK 11
- IntelliJ IDEA Community
- Maven
- Tomcat, Jetty
- MariaDB
- MyBatis

## 2. Spring MVC 환경 구축
- web.xml 기반 설정
- DispatcherServlet 수동 등록
- MyBatis 연동 및 DB 조회 확인

## 3. Spring Boot 환경
- 내장 Tomcat
- 최소 설정으로 서버 실행 가능

# 2주차 과제- API 명세서 작성

## 접속자 수
### 요청 URL
Get /api/visitors

### Request Parameters
|name|type|description|note|
|------|---|---|---|
|startDate|String|조회 시작 날짜|yyyy-mm-dd
|endDate|String|조회 종료 날짜|yyyy-mm--dd
|type|String|집계 단위|DAILY/TOTAL

### Response Body
```
{
    "period": {
    "startDate": "2025-01-01",
    "endDate": "2025-01-07"
    },
  "totalVisitors": 1245,
  "dailyVisitors": [
    { "date": "2025-01-01", "count": 180 },
    { "date": "2025-01-02", "count": 210 }
  ]
}
```

## 부서별 접속자 수
Get /api/visitors/department

### Request Parameters
|name|type|description|note|
|------|---|---|---|
|startDate|String|조회 시작 날짜|yyyy-mm-dd
|endDate|String|조회 종료 날짜|yyyy-mm--dd

### Response Body

```
{
    "period": {
        "startDate": "2025-01-01",
        "endDate": "2025-01-07"
        },
    
    "departments": [
        {
            "departmentId": 1,
            "departmentName": "개발팀",
            "visitorCount": 420
        },
        {
            "departmentId": 2,
            "departmentName": "기획팀",
            "visitorCount": 315
        }
    ]
}
```

## 로그인 요청 수

Get /api/logins

### Request Parameters
|name|type|description|note|
|------|---|---|---|
|startDate|String|조회 시작 날짜|yyyy-mm-dd
|endDate|String|조회 종료 날짜|yyyy-mm--dd
|status|String|로그인 결과|SUCCESS/FAIL
### Response Body
```
{
    "totalLoginRequests": 980, 
    "successCount": 870,
    "failCount": 110,
    "dailyLogins": [
        {
            "date": "2025-01-01",
            "success": 120,
            "fail": 15
        }
    ]
}
```

## 게시글 작성 수
Get /api/posts/count

### Request Parameters
|name|type|description|note|
|------|---|---|---|
|startDate|String|조회 시작 날짜|yyyy-mm-dd
|endDate|String|조회 종료 날짜|yyyy-mm--dd

### Response Body
```
{
    "totalPostCount": 356,
    "dailyPostCount": [
        {
            "date": "2025-01-01",
            "count": 42
        },
        {
            "date": "2025-01-02",
            "count": 55
        }
    ]
}

```

