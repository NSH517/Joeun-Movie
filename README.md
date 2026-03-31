<div align="center">

<img src="https://img.shields.io/badge/🎬_MOVIE-E50914?style=for-the-badge&logoColor=white" height="50"/>

# 🎥 MOVIE — 영화 리뷰 · 토너먼트 플랫폼

> 내가 사랑한 영화를 리뷰하고, 최애 영화를 토너먼트로 가려보세요 🍿
<img width="1894" height="953" alt="1 메인페이지" src="https://github.com/user-attachments/assets/f234c562-1ed6-4bea-bfef-226318c96f1e" />


</div>

---

## 📌 프로젝트 개요

| 항목 | 내용 |
|------|------|
| 📅 개발 기간 | 2025-12-17 ~ 2025-12-30 |
| 👥 팀 구성 | 4인 팀 프로젝트 |
| 🔗 GitHub | [MSA15_1 Repository](https://github.com/MoaisMoa/MSA15_1-.git) |
| 💡 주요 기능 | 영화 목록 · 검색, 영화 상세 · 리뷰, 최애 영화 토너먼트, 회원 관리, 관리자 페이지 |
| 📊 PPT 링크 | https://docs.google.com/presentation/d/1K3n-e4S-NYc2_hfviU8CmYulb2HS2Oow/edit?slide=id.p1#slide=id.p1 |
| 🎬 시연 영상 | https://www.youtube.com/watch?v=xkNmg4kmPro |

---

## 🛠 기술 스택

### Frontend
![JSP](https://img.shields.io/badge/JSP-FF6F00?style=for-the-badge)
![JSTL](https://img.shields.io/badge/JSTL-FF6F00?style=for-the-badge)
![jQuery](https://img.shields.io/badge/jQuery-0769AD?style=for-the-badge&logo=jquery&logoColor=white)
![Bootstrap 5](https://img.shields.io/badge/Bootstrap5-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)

### Backend
![Java](https://img.shields.io/badge/Java-007396?style=for-the-badge&logo=openjdk&logoColor=white)
![Servlet](https://img.shields.io/badge/JavaServlet-007396?style=for-the-badge&logo=java&logoColor=white)
![Apache Tomcat](https://img.shields.io/badge/Tomcat-F8DC75?style=for-the-badge&logo=apachetomcat&logoColor=black)

### Database
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)

### Tools
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)
![VS Code](https://img.shields.io/badge/VSCode-007ACC?style=for-the-badge&logo=visualstudiocode&logoColor=white)

---

## 👥 팀원 및 역할 분담

| 팀원 | 역할 | 주요 기능 |
|------|------|-----------|
| 전휘강 | 🎨 메인 · 검색 · 토너먼트 | 메인 페이지, 검색 기능, 영화 상세 페이지, 영화 토너먼트 |
| 김경화 | ✍️ 리뷰 시스템 | 리뷰 페이지 |
| 박희진 | 🔐 인증 · 마이페이지 | 회원가입, 로그인 페이지, 마이페이지 |
| 나승현 | 🛠 관리자 시스템 | 관리자 페이지 전체 |

---

## ✨ 기능 상세

### 🎨 전휘강 — 메인 페이지 · 검색 · 영화 상세 · 토너먼트

#### 🏠 메인 페이지

- **무한 슬라이드 배너**
  - 주요 영화 포스터를 자동 슬라이드 방식으로 순환 표시
  - 진행 바(Progress Bar)와 좌우 버튼으로 수동 탐색 가능
  - 배너 클릭 시 해당 영화 상세 페이지로 이동

- **영화 목록 가로 슬라이드**
  - DB에서 조회한 전체 영화 목록을 가로 스크롤 슬라이드로 구성
  - `JSTL forEach`로 영화 데이터를 카드 형태로 렌더링
  - 영화 포스터 · 제목 · 개봉 연도 표시 및 상세 페이지 연결

<details>
<summary><b>🎥 메인 페이지 보기</b></summary>

<br>

<img width="1894" height="953" alt="1 메인페이지" src="https://github.com/user-attachments/assets/b068c451-a3c2-456f-8780-d314f908e371" />

<img width="1896" height="953" alt="2 메인페이지 하단 영화목록 슬라이드" src="https://github.com/user-attachments/assets/5b6cbaa4-e333-426f-a259-3ee2d6a2d394" />


</details>

---

#### 🔍 검색 기능

- **키워드 기반 영화 검색**
  - 영화 제목을 키워드로 입력하면 DB에서 일치하는 영화 조회
  - `DetailServlet`에서 `keyword` 파라미터를 받아 `movieService.searchBy(keyword)` 처리
  - 검색 결과를 상세 페이지와 연결하여 자연스러운 탐색 흐름 구성



---

#### 🎬 영화 상세 페이지

- **영화 정보 조회**
  - `DetailServlet`에서 `movie_id` 파라미터를 받아 DB에서 영화 정보 조회
  - `MovieService.selectBy(map)`을 활용하여 단건 영화 정보 렌더링
  - 포스터 · 제목 · 개봉일 · 장르 · 줄거리 등 상세 정보 표시

- **리뷰 연동**
  - 영화 상세 페이지에서 해당 영화의 리뷰 목록 확인 가능
  - 리뷰 작성 · 수정 · 삭제 기능과 연결

<details>
<summary><b>🎥 영화 상세 페이지 보기</b></summary>

<br>

<img width="1896" height="952" alt="4 상세페이지" src="https://github.com/user-attachments/assets/fd4e5970-0f68-4c20-b199-4354d1fc9a55" />


</details>

---

#### 🏆 영화 토너먼트

- **라운드 선택 기반 토너먼트**
  - 16강 / 8강 / 4강 중 원하는 라운드 선택 후 시작
  - DB 전체 영화 목록을 JS 배열로 받아 토너먼트 풀 구성

- **Fisher-Yates Shuffle 기반 랜덤 대진 구성**
  - 매 시작마다 영화 순서를 무작위로 섞어 다양한 대진 제공
  - Vanilla JS로 라운드 진행 로직 직접 구현

- **라운드 진행 및 우승 처리**
  - 두 영화 중 선택한 영화가 다음 라운드로 진출
  - 최종 1편이 남을 때까지 라운드 반복 진행
  - 우승 영화 결과 화면 표시

<details>
<summary><b>🎥 토너먼트 페이지 보기</b></summary>

<br>

<img width="1913" height="879" alt="5 토너먼트페이지" src="https://github.com/user-attachments/assets/463f59c6-7992-4f8f-82b7-06c0861aa5c3" />
<img width="1912" height="956" alt="6 토너먼트 라운드중" src="https://github.com/user-attachments/assets/c3896569-3693-4f37-8dd0-483031ad675d" />
<img width="1896" height="952" alt="7 토너먼트 우승 영화 상세페이지" src="https://github.com/user-attachments/assets/5f431447-479d-4e20-b2f9-c7e3d3e48480" />


</details>

---

### ✍️ 김경화 — 리뷰 시스템

#### 💬 리뷰 페이지

- 영화별 리뷰 목록 조회
- 리뷰 작성 · 수정 · 삭제 기능 구현 (`ReviewServlet`, `ReviewWriteServlet`, `ReviewUpdateServlet`, `ReviewDeleteServlet`)
- `ReviewDAO` · `ReviewService` 계층 설계

---

### 🔐 박희진 — 인증 · 마이페이지

#### 🔑 로그인 / 회원가입 페이지

- 일반 로그인 및 로그아웃 처리 (`LoginServlet`, `LogoutServlet`)
- 회원가입 및 아이디 중복 확인 (`SignUpServlet`, `IdCheckServlet`)
- 로그인 성공 / 실패 페이지 분기 처리
- `AuthFilter` · `EncodingFilter` 기반 접근 제어 및 인코딩 처리
- `PersistenceLogins` 기반 자동 로그인 기능

#### 👤 마이페이지

- 회원 정보 조회 및 수정 (`MyPageInfoServlet`, `MyPageInfoUpdateServlet`)
- 작성 리뷰 목록 및 리뷰 상세 조회 (`MyPageReviewListServlet`, `MyPageReviewInfoServlet`)

---

### 🛠 나승현 — 관리자 시스템

#### 🎛 관리자 페이지

- 영화 목록 조회 · 상세 · 등록 · 수정 · 삭제 (`MovieServlet`, `MovieServletInfo`, `MovieUpdateServlet`, `MovieDeleteServlet`)
- 회원 목록 조회 · 상세 · 삭제 (`UsersServlet`, `UsersServletInfo`, `UserDeleteServlet`)
- 리뷰 전체 목록 조회 및 관리
- 관리자 전용 헤더 / 사이드바 레이아웃 구성 (`adminheader.jsp`, `adminsidebar.jsp`)

---

## 🗄 DB 설계 주요 테이블

```
users            — 회원 정보 (아이디, 비밀번호, 이름 등)
persistence_logins — 자동 로그인 토큰 관리
movie            — 영화 정보 (제목, 개봉일, 포스터 경로 등)
genre            — 장르 정보
movie_genre      — 영화-장르 다대다 연결
review           — 영화 리뷰 (작성자, 내용, 평점 등)
board            — 게시판
```

---

<div align="center">

**🎬 당신의 최애 영화는 무엇인가요? 🍿**

</div>
