# 쿠 프로젝트

## 서버 

- 기술 : Spring Boot

클라이언트의 요청을 받으면 JSON 파일을 전송한다. (= API 구현)
게임 기동 시 게임의 상황을 계산한다.
플레이어 간의 통신 (웹소켓) 담당.

### 서버 담당

- 김현오
- 윤신요
- 조현석

### 서버 Repo

[GitHub - singateco/springbootcoup](https://github.com/singateco/springbootcoup)

## 클라이언트

- 기술  : React (Static site = 서버 없음)

JSON 파일을 불러와 유저에게 표시한다.
받은 JSON 파일로 화면을 구현한다. (로그인 창, 게시판, 게임 화면...)

### 클라이언트 담당

- 김현오
- 박준형
- 서형민
- 김종진

### 클라이언트 Repo

생성중

## 서버와 클라이언트의 정보 교류 예시

[JSONPlaceholder - Free Fake REST API](https://jsonplaceholder.typicode.com/) 가상 API

### 예상 시나리오 1

유저가 게시글 목록을 볼수 있는 페이지를 연다.
자바스크립트로 렌더 하기 전 api로 게시글 목록을 불러온다.
(GET serverurl.com/boardlist?page=1)

JSON 파일로 게시글 목록이 반환됨.
```json
[
  {
    "userId": 1,
    "id": 1,
    "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
    "body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto"
  },
  {
    "userId": 1,
    "id": 2,
    "title": "qui est esse",
    "body": "est rerum tempore vitae\nsequi sint nihil reprehenderit dolor beatae ea dolores neque\nfugiat blanditiis voluptate porro vel nihil molestiae ut reiciendis\nqui aperiam non debitis possimus qui neque nisi nulla"
  },
  {
    "userId": 1,
    "id": 3,
    "title": "ea molestias quasi exercitationem repellat qui ipsa sit aut",
    "body": "et iusto sed quo iure\nvoluptatem occaecati omnis eligendi aut ad\nvoluptatem doloribus vel accusantium quis pariatur\nmolestiae porro eius odio et labore et velit aut"
  },
  {
    "userId": 1,
    "id": 4,
    "title": "eum et est occaecati",
    "body": "ullam et saepe reiciendis voluptatem adipisci\nsit amet autem assumenda provident rerum culpa\nquis hic commodi nesciunt rem tenetur doloremque ipsam iure\nquis sunt voluptatem rerum illo velit"
  },
  {
    "userId": 1,
    "id": 5,
    "title": "nesciunt quas odio",
    "body": "repudiandae veniam quaerat sunt sed\nalias aut fugiat sit autem sed est\nvoluptatem omnis possimus esse voluptatibus quis\nest aut tenetur dolor neque"
  },
  {
    "userId": 1,
    "id": 6,
    "title": "dolorem eum magni eos aperiam quia",
    "body": "ut aspernatur corporis harum nihil quis provident sequi\nmollitia nobis aliquid molestiae\nperspiciatis et ea nemo ab reprehenderit accusantium quas\nvoluptate dolores velit et doloremque molestiae"
  },
  {
    "userId": 1,
    "id": 7,
    "title": "magnam facilis autem",
    "body": "dolore placeat quibusdam ea quo vitae\nmagni quis enim qui quis quo nemo aut saepe\nquidem repellat excepturi ut quia\nsunt ut sequi eos ea sed quas"
  },
  {
    "userId": 1,
    "id": 8,
    "title": "dolorem dolore est ipsam",
    "body": "dignissimos aperiam dolorem qui eum\nfacilis quibusdam animi sint suscipit qui sint possimus cum\nquaerat magni maiores excepturi\nipsam ut commodi dolor voluptatum modi aut vitae"
  }
]
```

JSON 파일을 받은 클라이언트는 `JSON.parse()` 를 이용해 게시글 목록을 표시한다.
