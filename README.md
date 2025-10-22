# Choicely 정책 및 공유 페이지

GitHub Pages를 통해 호스팅되는 Choicely 앱의 정책 페이지와 공유 기능을 위한 정적 웹페이지입니다.

## 파일 구조

```
choicelyPolicy/
├── index.html              # 개인정보처리방침 메인 페이지
├── share.html              # 직관 분석 공유 페이지 (썸네일 포함)
├── share-logical.html      # 논리 분석 공유 페이지 (썸네일 포함)
├── style.css               # CSS 스타일시트
└── README.md               # 프로젝트 설명서
```

## 공유 기능 설명

### 🎯 목적
OneLink 무료 플랜에서는 썸네일 이미지를 지원하지 않으므로, 무료로 썸네일이 포함된 공유 기능을 구현하기 위해 링크 래핑 방식을 사용합니다.

### 🔄 동작 원리
1. **카카오톡 스크래퍼**: `share.html` 페이지를 방문하여 Open Graph 태그를 읽어 썸네일 생성
2. **사용자 클릭**: 썸네일을 클릭하면 `share.html` 페이지가 열림
3. **자동 리디렉션**: 0.1초 후 OneLink(`https://onelink.to/6m2v9r`)로 자동 이동
4. **앱 다운로드**: OneLink가 사용자 OS를 감지하여 적절한 스토어로 이동

### 📱 공유 페이지 종류
- **직관 분석**: `share.html` - 타로 카드 분석 결과 공유
- **논리 분석**: `share-logical.html` - 논리적 프레임워크 분석 결과 공유

## GitHub Pages 설정 방법

### 1. GitHub 저장소 생성

1. GitHub에 로그인
2. "New repository" 클릭
3. Repository name: `choicelyPolicy` (또는 원하는 이름)
4. Public으로 설정
5. "Create repository" 클릭

### 2. 파일 업로드

1. 생성된 저장소에서 "uploading an existing file" 클릭
2. `index.html`, `share.html`, `share-logical.html`, `style.css` 파일을 드래그 앤 드롭
3. Commit message 작성 후 "Commit changes" 클릭

### 3. GitHub Pages 활성화

1. 저장소의 "Settings" 탭 클릭
2. 왼쪽 메뉴에서 "Pages" 클릭
3. Source를 "Deploy from a branch"로 설정
4. Branch를 "main"으로 선택
5. "Save" 클릭

### 4. 사이트 접속

- **개인정보처리방침**: `https://[사용자명].github.io/choicelyPolicy/`
- **직관 분석 공유**: `https://[사용자명].github.io/choicelyPolicy/share.html`
- **논리 분석 공유**: `https://[사용자명].github.io/choicelyPolicy/share-logical.html`

### 5. 앱에서 링크 업데이트

앱의 `ShareService`에서 링크를 실제 GitHub Pages URL로 변경하세요:

```dart
static const String _intuitiveShareLink = 'https://[사용자명].github.io/choicelyPolicy/share.html';
static const String _logicalShareLink = 'https://[사용자명].github.io/choicelyPolicy/share-logical.html';
```

## 커스터마이징

### 회사 정보 수정

`index.html` 파일에서 다음 부분을 수정하세요:

- `[회사명]`: 실제 회사명으로 변경
- `[담당자명]`: 개인정보 보호책임자 이름
- `[전화번호]`: 연락처
- `[이메일주소]`: 이메일 주소
- `[위탁업체명]`, `[위탁업무 내용]`: 개인정보 처리 위탁 정보

### 스타일 수정

`style.css` 파일에서 색상, 폰트, 레이아웃 등을 자유롭게 수정할 수 있습니다.

## 특징

- ✅ 반응형 디자인 (모바일, 태블릿, 데스크톱 지원)
- ✅ 깔끔하고 전문적인 디자인
- ✅ 접근성 고려
- ✅ 인쇄 친화적
- ✅ 애니메이션 효과
- ✅ SEO 최적화

## 라이선스

이 프로젝트는 MIT 라이선스 하에 배포됩니다.
