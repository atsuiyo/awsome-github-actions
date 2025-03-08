# 🚀 Awesome GitHub Actions

깃허브 저장소를 작성하면서 만든 GitHub Actions 워크플로우 모음집입니다. CI/CD 파이프라인을 쉽게 구축할 수 있는 다양한 워크플로우 템플릿을 제공합니다.

## 📋 목차

- [자동 릴리스](#자동-릴리스)
- [PyPI 배포](#pypi-배포)
- [라이센스](#라이센스)

## [🔄 자동 릴리스](./auto-release/README.md)

GitHub에서 자동으로 릴리스를 생성하는 워크플로우입니다.

- ✨ [**기본 자동 릴리스**](./auto-release/auto-release.yaml): `pyproject.toml`에서 버전을 읽고 CHANGELOG.md에서 릴리스 노트를 추출하여 GitHub 릴리스를 자동 생성합니다.
- 🐍 [**Python 패키지 자동 릴리스**](./auto-release/auto-release-python.yaml): Python 패키지의 자동 릴리스 워크플로우로, 빌드된 패키지 아티팩트를 함께 첨부합니다.

## [📦 PyPI 배포](./pypi/README.md)

Python 패키지를 PyPI에 자동으로 배포하는 워크플로우입니다.

- 📤 [**PyPI 릴리스**](./pypi/pypi.yaml): GitHub 릴리스 이벤트에 반응하여 UV 패키지 매니저를 사용해 PyPI에 패키지를 자동 배포합니다.

## 📄 라이센스

이 프로젝트는 MIT 라이센스 하에 배포됩니다. 자세한 내용은 [LICENSE](LICENSE) 파일을 참조하세요.
