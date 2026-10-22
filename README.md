# material-login-ui

**Material UI(MUI)로 만든 로그인 화면 하나짜리 React 예제**입니다. (2024-03, Vite + React + TypeScript)
MUI 공식 문서의 "Sign in" 템플릿을 옮겨 온 것으로, 화면만 있고 실제 로그인 처리(서버 통신)는 없습니다.

## 화면 내용

| 요소 | 내용 |
| --- | --- |
| 아바타 + 제목 | 자물쇠 아이콘, `Sign in` |
| 입력칸 | 이메일(`email`), 비밀번호(`password`) — 둘 다 필수 표시 |
| 체크박스 | `Remember me` (동작 연결 없음) |
| 버튼 | `Sign In` — 누르면 입력한 **이메일만** 브라우저 콘솔에 출력 |
| 링크 | `Forgot password?`, `Don't have an account? Sign Up` (이동 주소 없음, `#`) |
| 하단 | `Copyright © Your Website <올해>` 문구 (자리표시자) |

## 사용 기술

| 구분 | 내용 |
| --- | --- |
| 화면 | React 18.2, TypeScript 5.2 |
| 디자인 | MUI 5 (`@mui/material`, `@mui/icons-material`), Emotion, Roboto 글꼴 |
| 개발 환경 | Vite 5 (SWC 사용) |
| 코드 검사 | ESLint 8 |

## 폴더 구조

```
material-login-ui/
├── index.html
├── package.json
├── vite.config.ts
└── src/
    ├── main.tsx      # 시작점 (글꼴 불러오기 + SignIn 표시)
    └── SignIn.tsx    # 로그인 화면 전체
```

## 실행 명령

| 명령 | 설명 |
| --- | --- |
| `npm run dev` | 개발 서버 (http://localhost:5173) |
| `npm run build` | 타입 검사 후 배포용 파일 생성 (`dist/`) |
| `npm run preview` | 빌드 결과 미리보기 |
| `npm run lint` | ESLint 검사 |

## 실행 방법

```bash
git clone https://github.com/jeong-jihyun/material-login-ui.git
cd material-login-ui
npm ci
npm run dev
```

Node.js 22에서 `npm ci`, `npm run build`, `npm run lint`가 성공하는 것을 확인했습니다. (브라우저 화면은 확인하지 못했습니다.)

## 개선 내역 (2026-10)

| 구분 | 문제 | 수정 내용 |
| --- | --- | --- |
| 보안 | 로그인 버튼을 누르면 이메일과 **비밀번호 원문**을 콘솔에 출력 | 비밀번호 출력 제거 (이메일만 출력) |
| 글꼴 | `@fontsource/roboto`를 설치만 하고 불러오지 않아 MUI가 기대하는 Roboto 글꼴이 적용되지 않음 | `main.tsx`에서 300·400·500·700 두께 불러오기, 빌드 성공 확인 |

## 앞으로 손보면 좋은 점

- 실제 로그인이 되려면 `handleSubmit`에서 서버 API를 호출하는 코드를 넣어야 합니다.
- 하단 `Your Website` 문구와 링크 주소(`#`)는 템플릿 그대로입니다.
- `SignIn.tsx`의 `TODO remove` 주석처럼 불필요한 테마 초기화가 남아 있습니다.
- 테스트 코드가 없습니다.
