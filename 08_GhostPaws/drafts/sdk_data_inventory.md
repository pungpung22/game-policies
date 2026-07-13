# Ghost Paws SDK 및 데이터 처리 목록

검토일: 2026년 7월 13일

| 구성요소 | 포함 | 기기 밖 전송 | 용도/비고 |
|---|---:|---:|---|
| Godot Engine 4.7 | 예 | 기본 런타임 자체는 아니요 | 게임 런타임 |
| 로컬 저장/텔레메트리 | 예 | 아니요 | 진행, 재화, 설정, 런 결과, 광고 날짜/횟수, 저장 백업 |
| Poing Godot AdMob 4.3.1 | 예 | 예 | Android/iOS Google Mobile Ads 연결 |
| Google Mobile Ads Android 24.9.0 | 예 | 예 | 보상 광고, 측정, 보안·부정행위 방지 |
| Google Mobile Ads iOS 12.14.0 | 예 | 예 | 보상 광고, 측정, 보안·부정행위 방지 |
| Google UMP iOS 3.1.0 / Android SDK 간접 의존성 | 예 | 예 | 지역별 개인정보 메시지와 동의 상태 |
| 분석/충돌 보고 SDK | 아니요 | 해당 없음 | Firebase Analytics, Crashlytics, Sentry 미포함 |
| 계정/클라우드/소셜 SDK | 아니요 | 해당 없음 | 개발자 서버, 로그인, 채팅 없음 |
| 실제 IAP SDK | 아니요 | 해당 없음 | 카탈로그/복구 인터페이스만 있으며 provider 연결 전 출시 차단 |

## Google Mobile Ads가 처리할 수 있는 범주

- IP 주소와 이를 이용한 대략적 위치 추정
- 광고 ID, 앱 세트 ID, 앱·개발자 범위 식별자 등 기기/계정 식별자
- 앱 실행, 탭, 광고 노출, 동영상 시청 등 상호작용
- 비정상 종료, 실행 시간, 멈춤, 에너지 사용량 등 진단·성능
- 표시된 광고 등 광고 데이터

목적은 광고 제공, 측정·분석, 보안 및 부정행위 방지이며 Google 문서상 전송 중
TLS 암호화를 사용한다. mediation adapter는 현재 활성화하지 않는다.

## 권한 및 네트워크

- Android Gradle export와 `INTERNET`, `ACCESS_NETWORK_STATE` 사용
- Google Mobile Ads가 최종 manifest에 `AD_ID`를 선언할 수 있으므로 AAB에서 확인
- 위치, 연락처, 카메라, 마이크 권한 요청 없음
- iOS ATT 프롬프트 없음; IDFA 기반 추적을 의도하지 않음
- iOS AdMob 플러그인에 SKAdNetwork 목록과 privacy manifest가 포함되는지 archive에서 확인

## 출시 때마다 확인

1. 최종 AAB/IPA의 실제 SDK 버전, 간접 의존성, manifest와 privacy report를 추출한다.
2. Google의 최신 Android Data safety/iOS App Privacy 공개 문서와 대조한다.
3. Android/iOS 운영 App ID 및 보상 광고 단위 ID가 테스트 ID가 아닌지 확인한다.
4. UMP Privacy & messaging 양식, 개인정보 설정 진입점, 동의 거부/오프라인을 실기기에서 확인한다.
5. `app-ads.txt`의 `pub-9236878703920912` 행이 공개 루트에서 열리는지 확인한다.
6. mediation, 분석, 충돌 보고, IAP provider를 추가하면 이 목록과 모든 스토어 신고를 갱신한다.
