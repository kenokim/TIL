## create-react-app
my-react-app/
├── node_modules/         # 설치된 npm 패키지들
├── public/               # 정적 파일 (HTML, Favicon 등)
│   ├── index.html        # 메인 HTML 파일
│   ├── favicon.ico       # 파비콘 아이콘
│   ├── manifest.json     # PWA 관련 설정 파일
│   └── robots.txt        # 검색 엔진 크롤링 관련 설정
├── src/                  # 애플리케이션의 소스 코드
│   ├── assets/           # 이미지, 폰트, 스타일 등의 정적 파일
│   ├── components/       # 재사용 가능한 컴포넌트
│   ├── pages/            # 페이지 단위 컴포넌트 (라우팅 용도)
│   ├── hooks/            # 커스텀 훅 정의
│   ├── context/          # Context API 관련 파일
│   ├── utils/            # 유틸리티 함수들
│   ├── services/         # API 호출 및 비즈니스 로직 관련 모듈
│   ├── App.js            # 메인 애플리케이션 컴포넌트
│   ├── index.js          # React 애플리케이션 진입점
│   ├── routes.js         # 라우트 설정 파일
│   └── styles/           # 글로벌 스타일 (CSS, SCSS, Styled Components 등)
├── .gitignore            # Git에서 제외할 파일 목록
├── package.json          # 프로젝트 설정 및 종속성 관리 파일
├── package-lock.json     # 종속성 버전 잠금 파일
├── README.md             # 프로젝트 설명 문서
└── webpack.config.js     # 웹팩 설정 파일 (사용하는 경우)

