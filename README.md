# 스마트 워시 케어 (Android Studio / Kotlin Jetpack Compose)

## 들어 있는 기능
- 환영/로그인(기기 내 임시 이름 저장; 서버 인증 아님), 홈
- 스마트폰 카메라 촬영 / 갤러리 이미지 가져오기
- ML Kit 한국어 인쇄 텍스트 OCR 및 텍스트 기반 세탁 정보 추출
- 분석 결과 확인/수정, 내 옷장 저장/검색/상세/삭제
- 색상 및 세탁 정보별 세탁 그룹 제안, 그룹 저장/삭제
- 로컬 저장소 이용(별도 서버 필요 없음)

## 실행
1. 압축 해제 후 Android Studio에서 **Open** → `SmartWashCare` 폴더를 선택합니다.
2. Gradle JVM은 JDK 17로 설정합니다. Android SDK Platform 35를 설치합니다.
3. 최초 Sync 때 Android Gradle Plugin / Kotlin / ML Kit 라이브러리 다운로드를 위해 인터넷이 필요합니다.
4. Android Studio의 내장 Gradle 또는 설치된 Gradle 8.9로 동기화합니다. 현재 배포 환경에서는 Gradle wrapper JAR을 가져올 수 없어 포함하지 않았습니다. 로컬에 Gradle 8.9가 있다면 프로젝트 폴더에서 `gradle wrapper --gradle-version 8.9` 실행 후 `./gradlew assembleDebug` (Windows: `gradlew.bat assembleDebug`) 로 APK 빌드할 수 있습니다.
5. `app` 실행 구성을 선택하고 에뮬레이터 또는 USB 디버깅을 켠 실기기에서 ▶ Run을 누릅니다.
6. 직접 APK 빌드 시 `app/build/outputs/apk/debug/app-debug.apk` 파일을 스마트폰에 설치할 수 있습니다.

## 중요 제한
- **실제 실행 및 빌드 성공은 여기서 검증하지 못했습니다.** Android SDK / Gradle 빌드 환경이 없어 APK는 포함하지 않습니다.
- QR/기호 모양 세탁표시를 컴퓨터 비전으로 판독하는 기능은 구현하지 않았습니다. OCR은 텍스트만 읽습니다. 분석 결과는 사용자가 반드시 검토/수정하세요.
- 소셜 카카오 계정 인증, 클라우드 동기화는 구현되지 않았습니다.
- 촬영은 다른 카메라 앱을 호출하는 Android `TakePicture` 계약입니다. 시뮬레이터 카메라가 없으면 갤러리 선택 기능을 사용하세요.
