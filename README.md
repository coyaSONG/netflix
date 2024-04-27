# [Demo 보기 🖥️ ](https://netflix-six-woad.vercel.app/)

# 프로젝트 기술 스택

이 프로젝트에서 사용된 주요 기술 스택:

- **Frontend**: ReactJS, Next.js, Tailwind CSS
- **Backend**: Prisma, MongoDB
- **Authentication**: NextAuth

## 문제 해결

### 문제: Favorite API 구현 중 POST 요청 시 400 에러 발생

**원인**: GET 요청과 달리, POST, DELETE와 같이 데이터를 변경하는 요청은 CSRF 공격을 방지하기 위해 보다 엄격한 보안 기능과 세션 관리 기능이 필요.

**해결 방법**:

1. `...nextauth.js` 파일에서 옵션을 따로 분리.
2. `serverAuth.js` 파일에서 `getSession`을 `getServerSession`으로 변경하고, `req`, `res`를 `serverAuth` 파라미터에 함께 전달하여 해결함. 참조 [Stack Overflow](https://stackoverflow.com/questions/77408979/nextauth-js-getsession-in-api-works-with-get-fails-with-post)

### 오류: 배포 후에 로그인에서 다음 페이지들로 라우팅이 안되는 오류 발생

**원인**: 최신버전 Next.js에서는 환경변수에 `NEXTAUTH_URL`를 넣어줘야함.

**해결 방법**: 환경변수에 배포로 얻은 내 Vercel URL을 넣어줘서 해결
