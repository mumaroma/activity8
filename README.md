⏱️ 두 운동 비교 시뮬레이션 (Motion Simulator)

중학교 2~3학년 수학 및 과학 교과에서 다루는 등속 운동과 위치-시간 그래프의 관계를 시각적으로 탐구할 수 있는 대화형 웹 시뮬레이션입니다.

학생들은 동적 자취(DMTG: Dynamic Motion Trace Graph), 위치-시간 그래프, 그리고 실시간 데이터 테이블의 유기적인 동기화를 관찰하며 추론 능력을 기를 수 있습니다.

✨ 핵심 기능

동적 자취 트랙 (DMTG): 일정 시간 간격마다 객체의 위치를 수직선 위에 점(토큰)으로 남겨 속도의 시각적 흐름을 보여줍니다.

실시간 위치-시간 그래프: $X$축(시간)과 $Y$축(위치) 격자가 실시간으로 렌더링되며, 현재 시간에 맞춰 펄스 애니메이션이 동기화됩니다.

양방향 인터랙티브 드래그: 그래프 양 끝의 대형 원 핸들을 위아래로 드래그하여 두 객체의 출발 위치와 종료 위치(속도 및 방향)를 즉시 디자인할 수 있습니다.

실시간 누적 데이터 테이블: 시간 경과에 따라 운동 데이터가 실시간으로 쌓이며, 현재 흐르고 있는 시간이 표에서 하이라이트 처리됩니다.

반응형 레이아웃: 데스크탑(가로 나란히 보기)과 모바일/태블릿(세로 흐름 보기) 모드를 원클릭으로 전환할 수 있습니다.

🚀 배포 및 실행 방법

이 프로젝트는 단일 HTML 파일 배포(추천)와 React 개발 환경 배포의 두 가지 방식으로 활용할 수 있습니다.

방법 A. 초간단 단일 HTML 배포 (추천 ⭐)

복잡한 개발 도구 설치(Node.js, npm 등) 없이 파일 하나만으로 GitHub Pages에 배포하는 방식입니다. 학교 수업이나 빠른 공유에 가장 적합합니다.

GitHub에 새 저장소(Repository)를 생성합니다.

제공된 로컬 실행용 단일 HTML 코드의 내용을 복사하여 index.html이라는 이름으로 저장소 루트에 업로드합니다.

저장소의 Settings -> Pages 메뉴로 이동합니다.

Build and deployment 항목의 Branch를 main (또는 master)로 지정하고 Save를 누릅니다.

약 1분 후 제공되는 URL(예: https://사용자이름.github.io/저장소이름)로 접속하면 시뮬레이션이 즉시 실행됩니다.

방법 B. React / Vite 프로젝트로 구성하기 (개발자용)

React 컴포넌트인 App.jsx를 기반으로 정식 웹 프로젝트를 빌드하고 배포하는 방법입니다.

1. 프로젝트 초기화 (Vite 사용)

# Vite를 이용한 React 프로젝트 생성
npm create vite@latest motion-simulator -- --template react

# 프로젝트 디렉토리 이동 및 의존성 설치
cd motion-simulator
npm install

# Lucide 아이콘 및 Tailwind CSS 설치
npm install lucide-react
npm install -D tailwindcss @tailwindcss/vite


2. 설정 파일 적용 (Vite + Tailwind)

vite.config.js 파일에 Tailwind 플러그인을 연결합니다:

import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'
import tailwindcss from '@tailwindcss/vite'

export default defineConfig({
  plugins: [react(), tailwindcss()],
  base: '/<your-repository-name>/', // GitHub Pages 배포를 위한 가상 경로 설정
})


3. 코드 배치

에디터에 열려있는 App.jsx 전체 코드를 src/App.jsx에 덮어씌웁니다.

src/main.jsx에서 App 컴포넌트가 올바르게 렌더링되고 있는지 확인합니다.

4. GitHub Pages 배포 자동화

# 배포 패키지 설치
npm install -D gh-pages


package.json 파일의 scripts 영역에 아래 명령어를 추가합니다:

"scripts": {
  "predeploy": "npm run build",
  "deploy": "gh-pages -d dist",
  "dev": "vite",
  "build": "vite build",
  "preview": "vite preview"
}


이제 아래 명령어를 실행하면 빌드와 GitHub Pages 배포가 한 번에 완료됩니다:

npm run deploy


📂 프로젝트 구조 (React 기준)

motion-simulator/
├── public/
├── src/
│   ├── App.jsx          # 시뮬레이션 메인 로직 및 UI 컴포넌트
│   ├── main.jsx         # React 진입점
│   └── index.css        # Tailwind CSS 적용 파일
├── package.json         # 프로젝트 의존성 및 스크립트
├── vite.config.js       # Vite 빌드 설정
└── README.md            # 프로젝트 안내서


📄 라이선스

This project is licensed under the MIT License - see the LICENSE file for details.
