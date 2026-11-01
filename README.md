# NoteS26 APK 빌드 방법

## 방법 A: GitHub Actions (설치 없이, 권장)
1. GitHub에서 새 저장소를 만들고 이 폴더의 내용을 전부 업로드(push)합니다.
2. 저장소의 Actions 탭 → "Build APK" 워크플로가 자동 실행됩니다. (안 되면 Run workflow)
3. 완료 후 Artifacts의 `NoteS26-debug-apk`를 내려받아 압축을 풀면 `app-debug.apk`가 있습니다.
4. 폰에서 "출처를 알 수 없는 앱 설치"를 허용하고 설치하세요.

## 방법 B: 내 PC에서 빌드
필요: Node.js 18+, JDK 17, Android Studio(SDK 포함)
```
npm install
npx cap add android
npx cap sync android
cd android && ./gradlew assembleDebug
```
결과: android/app/build/outputs/apk/debug/app-debug.apk

## 참고
- 이 HTML은 Tailwind, Font Awesome, Google Fonts를 CDN에서 불러오므로 앱 실행 시 인터넷 연결이 필요합니다.
- 이 APK는 debug 서명이라 개인 설치/테스트용입니다. Play 스토어 배포는 release 서명이 필요합니다.
