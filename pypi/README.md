# 📦 PyPI 배포 액션

이 워크플로우는 Python 패키지를 자동으로 빌드하고 PyPI에 배포하는 GitHub 액션입니다.

## 📋 목차

- [주요 기능](#주요-기능)
- [사용 방법](#사용-방법)
- [워크플로우 실행 트리거](#워크플로우-실행-트리거)
- [고급 설정](#고급-설정)
- [참고사항](#참고사항)

## 🌟 [주요 기능](./pypi.yaml)

- 🔄 GitHub 릴리스 이벤트 시 자동 실행
- 🛠️ UV 패키지 매니저를 사용한 빠르고 안정적인 빌드
- 🔐 PyPI 보안 배포 지원 (OIDC)
- 📤 소스 배포 및 whl 배포 지원

## 🚀 사용 방법

### 설정 단계

1. 프로젝트 루트에 `.github/workflows/` 디렉토리를 생성합니다
2. 워크플로우를 복사하여 `.github/workflows/pypi.yaml`로 저장합니다

### 필요한 프로젝트 구성

- 프로젝트 루트에 올바르게 구성된 `pyproject.toml` 파일이 필요합니다

```toml
[project]
name = "your-package-name"
version = "0.1.0"
```

## 🔄 [워크플로우 실행 트리거](./pypi.yaml)

워크플로우는 다음 이벤트에 의해 트리거됩니다:

1. GitHub 릴리스 발행 시 (`release: published`)
2. 수동 실행 시 (`workflow_dispatch`)


## 📜 참고사항

- 이 워크플로우는 OIDC를 사용하여 PyPI에 인증합니다 (더 안전한 방법)
- `uv`를 사용하여 빌드 및 배포 속도를 최적화합니다
