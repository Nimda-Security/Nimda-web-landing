# NIMDA Web Landing Page

정보보안 동아리 **NIMDA**의 소개 및 지원 페이지입니다.

🌐 https://nimda.space/

## 기술 스택

- [Next.js 14](https://nextjs.org) (App Router, 정적 export)
- [Tailwind CSS](https://tailwindcss.com)
- [Framer Motion](https://www.framer.com/motion/) — 스크롤/진입 애니메이션
- [lucide-react](https://lucide.dev) — 아이콘

## 시작하기

```bash
npm install
npm run dev
```

브라우저에서 [http://localhost:3000](http://localhost:3000)을 열면 됩니다.

| 명령어          | 설명                          |
| --------------- | ----------------------------- |
| `npm run dev`   | 개발 서버 실행                |
| `npm run build` | 정적 사이트 빌드 (`out/`)     |
| `npm run start` | 프로덕션 서버 실행            |
| `npm run lint`  | ESLint 검사                   |

## 프로젝트 구조

```
src/
├── app/
│   ├── layout.js          # 메타데이터, 전역 폰트(Pretendard)
│   ├── page.js            # 랜딩 페이지 섹션 구성
│   ├── globals.css
│   └── fonts/             # 로컬 폰트 (Mulmaru, atoz, Geist)
├── components/Landing/    # 섹션별 컴포넌트 (Hero, Activities, Timeline 등)
└── constants.js           # 페이지 콘텐츠 데이터
public/                    # 이미지, 로고
```

## 콘텐츠 수정

페이지에 표시되는 텍스트는 대부분 [`src/constants.js`](src/constants.js)에서 관리합니다.

- `CLUB` — 동아리 이름, 소개 문구, 홈페이지·지원서 링크
- `ACTIVITIES` — 주요 활동 소개
- `AWARDS` — 수상 내역
- `ACTIVITIES_2025` — 연간 활동 타임라인 (이미지는 `public/`에 넣고 파일명만 지정)

매 학기 지원 링크(`CLUB.links.apply`)와 활동 내역을 갱신해 주세요.

## 배포

`next.config.js`에 `output: "export"`가 설정되어 있어 `npm run build` 시 `out/` 디렉터리에 정적 파일이 생성됩니다. 이 디렉터리를 정적 호스팅 서비스에 업로드하면 됩니다.

> 정적 export 환경이므로 `next/image` 최적화는 비활성화되어 있고(`images.unoptimized`), API Route·서버 기능은 사용할 수 없습니다.
