# 🔄 자동 릴리스 액션

이 폴더에는 GitHub에서 자동으로 릴리스를 생성하는 워크플로우 파일이 포함되어 있습니다.

## 📋 목차

- [제공되는 워크플로우](#제공되는-워크플로우)
- [CHANGELOG.md 형식 예시](#changelogmd-형식-예시)

## 📋 제공되는 워크플로우

### ✨ [기본 자동 릴리스](./auto-release.yaml) (`auto-release.yaml`)

`main` 브랜치에 푸시가 발생하면 자동으로 새 버전을 감지하고 GitHub 릴리스를 생성합니다.

#### 주요 기능
- 🔍 `pyproject.toml`에서 버전 정보 추출
- 📝 `CHANGELOG.md`에서 릴리스 노트 자동 추출
- 🏷️ 의미 있는 버전 태그 생성 (vX.Y.Z 형식)
- 🔄 기존 릴리스와 버전 비교 후 새 버전일 때만 릴리스 생성
- 🔖 `latest` 태그 자동 생성 및 업데이트로 항상 최신 버전 참조 가능

#### 설정 방법
1. 프로젝트 루트에 `.github/workflows/` 디렉토리를 생성합니다
2. 파일을 복사하여 `.github/workflows/auto-release.yaml`로 저장합니다
3. `pyproject.toml` 파일에 `version = "X.Y.Z"` 형식으로 버전을 명시합니다
4. `CHANGELOG.md` 파일에 각 버전별 변경 사항을 기록합니다 (예: `# vX.Y.Z`)

### 🐍 [Python 패키지 자동 릴리스](./auto-release-python.yaml) (`auto-release-python.yaml`)

기본 자동 릴리스 기능에 Python 패키지 빌드 및 아티팩트 첨부 기능이 추가된 워크플로우입니다.

#### 주요 기능
- 🔍 `pyproject.toml`에서 버전 정보 추출
- 📝 `CHANGELOG.md`에서 릴리스 노트 자동 추출
- 📦 UV를 사용한 Python 패키지 빌드
- 🔗 빌드된 패키지 파일을 릴리스에 첨부
- 🔖 `latest` 태그 자동 업데이트로 최신 패키지 버전 쉽게 참조 가능

#### 설정 방법
1. 프로젝트 루트에 `.github/workflows/` 디렉토리를 생성합니다
2. 이 파일을 복사하여 `.github/workflows/auto-release-python.yaml`로 저장합니다
3. `pyproject.toml` 파일에 패키지 정보와 버전을 명시합니다
4. `CHANGELOG.md` 파일에 각 버전별 변경 사항을 기록합니다

## 📝 CHANGELOG.md 형식 예시

```markdown
# v1.2.0

## 새로운 기능
- 사용자 인증 기능 추가
- 대시보드 UI 개선

## 버그 수정
- 로그인 페이지 오류 수정

# v1.1.0

## 새로운 기능
- 검색 기능 추가
```

## 🔖 latest 태그 활용하기

워크플로우는 버전 태그 외에도 `latest` 태그를 자동으로 생성하고 업데이트합니다:

- 최신 릴리스를 항상 `latest` 태그로 참조 가능
- 다운로드 URL에서 특정 버전 대신 `latest`를 사용할 수 있음
  ```
  https://github.com/username/repo/releases/download/latest/package.tar.gz
  ```
- 의존성 관리에서 최신 버전을 쉽게 참조 가능
- 릴리스될 때마다 자동으로 `latest` 태그가 최신 버전을 가리키도록 업데이트됨
