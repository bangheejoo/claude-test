# CLAUDE.md

이 파일은 Claude Code (claude.ai/code)가 이 저장소에서 작업할 때 참고하는 안내 문서입니다.

## 프로젝트 개요

유명 명언을 표시하는 단일 페이지 정적 웹 애플리케이션(`index.html`)입니다. 순수 HTML, CSS, JavaScript만 사용하며 빌드 도구, 프레임워크, 외부 의존성이 없습니다.

## 실행 방법

브라우저에서 `index.html`을 직접 열거나, 정적 파일 서버로 실행합니다:

```bash
npx serve .
# 또는
python -m http.server 8080
```

## 아키텍처

모든 코드가 `index.html` 단일 파일 안의 세 섹션으로 구성됩니다:

- **`<style>`** — 전체 CSS. Flexbox 기반 다크 테마 레이아웃. 명언 카드 전환 시 JS가 `.fade` 클래스를 토글하여 페이드 효과를 구현합니다.
- **`<body>`** — 정적 HTML 껍데기. 명언 내용은 JS가 런타임에 주입합니다.
- **`<script>`** — 독립적인 모듈: `quotes` 배열, `show(index)` / `goTo(index)` 함수, 점 인디케이터 렌더링, 키보드·버튼 이벤트 리스너로 구성됩니다.

외부 에셋, 폰트, 네트워크 요청 없음.
