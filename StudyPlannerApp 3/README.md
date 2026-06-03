# StudyPlanner (iOS / Xcode)

기존 단일 HTML 웹앱(StudyPlanner)을 SwiftUI + WKWebView로 래핑한 네이티브 iOS 프로젝트입니다.

## 실행 방법
1. `StudyPlanner.xcodeproj`를 Xcode에서 엽니다 (Xcode 15 이상 권장).
2. 상단에서 시뮬레이터(예: iPhone 15)나 실기기를 선택합니다.
3. ⌘R 로 빌드 & 실행합니다.

## 구조
- `StudyPlanner/StudyPlannerApp.swift` — 앱 진입점
- `StudyPlanner/ContentView.swift` — 루트 화면
- `StudyPlanner/WebView.swift` — WKWebView 래퍼 (Web/index.html 로드)
- `StudyPlanner/Web/index.html` — 원본 웹앱 (그대로 번들 포함)
- `StudyPlanner/Info.plist` — 다크모드 / 세로 고정

## 참고
- 데이터는 웹앱의 `localStorage`에 저장되며 `WKWebView` 기본 데이터 저장소를 사용해 앱 재실행 후에도 유지됩니다.
- AI 분석 기능은 `https://api.anthropic.com` 호출을 사용합니다. 실제 기기에서 동작하려면 유효한 인증/프록시 설정이 필요할 수 있습니다.
- 실기기 빌드 시 `PRODUCT_BUNDLE_IDENTIFIER`(현재 `com.example.StudyPlanner`)와 Signing Team을 본인 계정으로 바꾸세요.
- 웹앱을 수정하려면 `Web/index.html`만 교체하면 됩니다.
