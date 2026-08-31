# 다시콕 (DasiKoK) Privacy Policy — GitHub Pages 배포 준비

이 폴더는 GitHub Pages로 게시할 **완전히 독립된 정적 사이트**입니다 — 앱 소스 코드나
`docs/`(프로젝트 내부 엔지니어링 문서)와는 별개이며, 이 폴더 자체가 실제 배포될 사이트의 전체
내용입니다.

**아직 GitHub에 실제 저장소를 만들거나 업로드하지 않았습니다.** 아래는 사용자 승인 후 실행할 절차만
정리한 것입니다.

## 파일 구성

- `index.html` — 한국어 개인정보처리방침(기본/루트 페이지)
- `privacy-en.html` — 영어 개인정보처리방침
- 두 페이지 모두 JavaScript 없음, 댓글/편집 UI 없음, 순수 정적 HTML — Google Play의 Privacy Policy
  요구사항(공개 접근 가능 / 지역 제한 없음 / 사용자가 편집 불가능 / PDF 아님)을 전부 충족하는 형태로
  작성됨.
- 페이지 상단에 서로를 가리키는 언어 전환 링크 포함(한국어 ↔ 영어).
- `<title>` 태그에 "Privacy Policy"가 명시되어 있어(한국어판도 "개인정보처리방침 (Privacy Policy)"
  형태로 병기) 리뷰어가 즉시 식별 가능.
- 앱 이름(다시콕/DasiKoK), developer name(DasiKoK), 문의 이메일(rednathfel@nate.com) 전부 반영됨.

## 배포 절차 (승인 후 실행)

### 방법 A — 이 폴더만을 위한 새 저장소 (권장, "별도 사이트" 요구사항에 가장 부합)

1. GitHub에서 새 public 저장소 생성(예: `dasikok-privacy`).
2. 이 `privacy-site/` 폴더의 두 HTML 파일(+본 README)을 그 저장소의 루트에 업로드(git init → add →
   commit → push, 또는 GitHub 웹 UI로 직접 업로드).
3. 저장소 Settings → Pages → Source를 "Deploy from a branch" → `main` 브랜치 `/ (root)`로 설정.
4. 몇 분 후 `https://<github-사용자명>.github.io/dasikok-privacy/`(한국어)와
   `https://<github-사용자명>.github.io/dasikok-privacy/privacy-en.html`(영어)에서 접근 가능.
5. 두 URL이 실제로 열리는지, HTTPS 자물쇠 아이콘이 정상인지 브라우저로 직접 확인.

### 방법 B — 이 프로젝트(다시콕 앱) 저장소의 `/docs` 폴더로 게시 (더 간단하지만 "별도 사이트"와는
다름)

이 프로젝트 저장소가 나중에 GitHub에 push되면, 저장소 루트의 `docs/` 폴더를 GitHub Pages 소스로
지정하는 방법도 있음 — 단, 그러면 앱 엔지니어링 문서(RISK_REGISTER.md 등)와 같은 폴더 이름을
공유하게 되어 혼동 소지가 있고, 사용자가 요청한 "별도 사이트" 요건과는 맞지 않아 **권장하지 않음**.
방법 A를 기본으로 함.

## 배포 후 해야 할 일

- `app/app/src/main/kotlin/com/dasikok/app/ui/PrivacyPolicyScreen.kt`의 클래스 doc 주석("no publicly
  hosted URL exists for this policy yet")을 실제 URL로 갱신.
- `docs/RELEASE.md`의 Privacy Policy 섹션에 실제 게시된 URL 기록.
- Play Console 앱 생성 시 Privacy Policy 필드에 한국어판 URL(기본) 등록 — Play Console 자체는 언어별
  URL을 따로 요구하지 않으므로, 페이지 안의 언어 전환 링크로 영어판에 도달 가능하게 하는 현재 구조로
  충분함.

## 아직 하지 않은 것 (사용자 승인 필요)

- GitHub 저장소 실제 생성
- 실제 파일 업로드/push
- GitHub Pages 활성화
- Play Console에 URL 등록
