# 원연정 — Fashion × AI 포트폴리오

패션 도메인 지식과 AI를 연결하는 포트폴리오 & 기술 블로그 사이트.
빌드 도구 없이 순수 HTML로 구성되어 있어, 브라우저에서 `index.html`을 열면 바로 확인할 수 있습니다.

## 디렉토리 구조

```
├── index.html          # 메인 페이지 (사이트 진입점 — 루트 유지)
├── pages/              # 메인 서브페이지
│   ├── about.html          # 소개
│   ├── projects.html       # 프로젝트 목록 (CV 베이직 · STL 카드)
│   ├── trend-log.html      # 트렌드 로그 (글 목록)
│   └── contact.html        # 연락처
├── posts/              # 세부 콘텐츠
│   ├── trend-log/          # 트렌드 로그 세부 글
│   │   ├── trend-log-01.html   # 글: 2026 Summer, 글로벌 패션 산업의 AI 지도
│   │   └── trend-log-02.html
│   └── projects/           # 프로젝트 콘텐츠
│       ├── cv-projects/        # 패션 CV 베이직 프로젝트 (스터디 시리즈)
│       │   ├── index.html          # 시리즈 메인 (로드맵 · 요약 표 · 카드)
│       │   ├── projects/           # 프로젝트 상세 페이지
│       │   │   ├── p1_classification.html   # P1 패션 아이템 분류
│       │   │   ├── p2_parsing.html          # P2 패션 이미지 파싱
│       │   │   ├── p3_segmentation.html     # P3 세그멘테이션 · 속성 태깅
│       │   │   ├── p4_virtual_tryon.html    # P4 가상 피팅 벤치마크 (인터랙티브 데모 내장)
│       │   │   ├── p5_generation.html       # P5 Text-to-Fashion 생성 (인터랙티브 데모 내장)
│       │   │   └── p9_trend_lifecycle.html  # STL 트렌드 수명주기 분류 (독립 프로젝트)
│       │   └── assets/img/projects/         # 상세 페이지용 이미지 (p1~p5 결과 그래프, p4 샘플, p5 생성 결과)
│       └── stl/
│           └── index.html      # STL 트렌드 수명주기 라이브 데모 (p9 페이지에 iframe으로 매립)
├── assets/
│   └── images/         # 이미지 원본 소재 (profile-original.jpg 등, 웹에서 참조하지 않음)
└── docs/
    └── CONTACT.md      # 사이트 콘텐츠 원고 (경력/학력/연락처)
```

## 작업 규칙

- **index는 루트, 서브페이지는 `pages/`, 세부 콘텐츠는 `posts/`**: `index.html`만 루트에 두고, 메인 서브페이지(about, projects, trend-log, contact)는 `pages/`에, 세부 글·프로젝트는 `posts/` 아래(`posts/trend-log/`, `posts/projects/`)에 넣습니다.
- **트렌드 로그 새 글**: `posts/trend-log/trend-log-02.html` 형식으로 추가합니다. 글 안에서 서브페이지로 가는 링크는 `../../pages/about.html`, 메인은 `../../index.html`처럼 `../../`를 붙이고, `pages/trend-log.html`(목록)과 필요 시 `index.html`에 링크를 등록합니다.
- **폰트**: Pretendard 폰트가 각 HTML 안에 base64로 내장되어 있어 파일이 큽니다(페이지당 약 200KB+). 새 페이지를 만들 때는 기존 페이지를 복사해서 시작하면 폰트가 유지됩니다.
- **이미지 소재**: 웹에 쓰지 않는 원본 파일은 `assets/images/`에 보관합니다. 웹에서 참조할 이미지는 용량을 줄여서(리사이즈/압축) 사용하세요.
- **CV 베이직 새 프로젝트(P6~P8) 추가**: 상세 페이지는 `posts/projects/cv-projects/projects/`에, 이미지는 `posts/projects/cv-projects/assets/img/projects/pN/`에 넣습니다. 기존 P1~P5 페이지를 복사해 시작하면 디자인(내장 폰트·스타일)이 유지됩니다. 완료 시 `posts/projects/cv-projects/index.html`에서 해당 카드를 `<article class="card soon">` → `<a class="card" href="...">`로 바꾸고 `<span class="more-cta">→ 자세히 보기</span>`를 추가하세요.
- **썸네일 색상 규칙**: Projects 계열 카드는 어두운 톤(그레이·네이비), Trend Log 계열 카드는 밝은 톤(베이지·핑크·포그)을 사용합니다.
