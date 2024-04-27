현재 프로젝트에 사용된 주요 기술스택
nextjs, next auth, reactjs, tailwind, prisma, mongodb

# troubleshooting


## error: favorite api를 구현하는 과정에서 post요청 시 400에러 발생
## reason: get과 다르게 데이터를 변경시키는 post,delete 같은 요청은 csrf공격을 보호하기위해 엄격한 보안기능과 세션관리기능때문
## solve: 아래의 방법으로 해결함.
1. [...nextauth] file에서 옵션을 따로 분리
2. serverAuth file에서 getSession을 getServerSession으로 변경 후 serverAuth 파라미터에 req,res 같이 전달로 해결함.
   stackoverflow 링크[https://stackoverflow.com/questions/77408979/nextauth-js-getsession-in-api-works-with-get-fails-with-post]

## error: 배포 후에 로그인에서 다음 페이지들로 라우팅이 안되는 오류 발생.
## reason: 최신버전 nextjs에서는 환경변수에 NEXTAUTH_URL를 넣어줘야함.
## solve: 환경변수에 배포로 얻은 내 vervel url을 넣어줘서 해결함.

