# 마음과 사유

AI 시대의 심리적 혼란을 철학·심리학의 언어로 다루는, 상담자와 내담자를
위한 아카이브 사이트입니다. Eleventy(11ty)로 만든 정적 사이트로,
글은 마크다운 파일로 관리합니다.

## 새 글 올리는 법

1. `src/posts/` 폴더에 새 `.md` 파일을 만듭니다.
   파일명 형식: `날짜-영문슬러그.md` (예: `2026-09-10-my-post.md`)
2. 맨 위에 아래 형식으로 정보를 적습니다 (앞뒤 `---` 꼭 포함):

   ```
   ---
   layout: post.njk
   title: 글 제목
   date: 2026-09-10
   excerpt: 목록에 보일 한 줄 요약
   tag: 태그 (선택)
   ---
   ```

3. 그 아래부터 마크다운으로 본문을 씁니다.
   - `## 소제목` → 소제목
   - `- 항목` → 목록
   - `**강조**` → 굵은 글씨(포인트 컬러로 표시됨)
4. 저장하고 Netlify(또는 GitHub)에 올리면 자동으로 목록 맨 위에
   최신 글로 반영됩니다.

⚠️ 제목/요약 안에 작은따옴표(`'`)를 쓸 때는 전체를 큰따옴표로
감싸주세요. 예: `excerpt: "그는 '괜찮다'고 말했다"`

## 소개 페이지 수정

`src/about.md` 파일을 마크다운으로 직접 수정하면 됩니다.

## 로컬에서 미리보기

```bash
npm install
npm run start
```

브라우저에서 `http://localhost:8080` 접속.

## Netlify 배포

### 방법 A — GitHub 연동 (추천, 이후 글 올리기가 가장 편함)

1. 이 폴더를 GitHub 저장소에 업로드합니다.
2. [netlify.com](https://netlify.com) 가입 → "Add new site" →
   "Import an existing project" → GitHub 저장소 선택.
3. 빌드 설정은 `netlify.toml`에 이미 들어있어 자동 인식됩니다.
   - Build command: `npm run build`
   - Publish directory: `_site`
4. Deploy 클릭. 이후 GitHub에 새 글(.md 파일)을 올릴 때마다
   Netlify가 자동으로 다시 빌드해 사이트에 반영합니다.

### 방법 B — 폴더 드래그 앤 드롭 (가장 빠름, 대신 매번 수동 재배포)

1. 로컬에서 `npm install && npm run build` 실행 → `_site` 폴더 생성.
2. [app.netlify.com/drop](https://app.netlify.com/drop) 접속 →
   `_site` 폴더를 통째로 끌어다 놓기.
3. 글을 추가할 때마다 이 과정을 반복해야 합니다.

처음 시작하고 글을 계속 업데이트할 계획이라면 **방법 A(GitHub 연동)**를
추천합니다.
