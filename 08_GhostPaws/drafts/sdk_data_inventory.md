# Ghost Paws SDK 및 데이터 처리 목록

검토일: 2026년 7월 12일

| 구성요소 | 현재 포함 | 기기 밖 전송 | 용도/비고 |
|---|---:|---:|---|
| Godot Engine 4.7 | 예 | 아니요 | 게임 런타임. iOS PrivacyInfo에 파일 timestamp, system boot time, disk space required-reason API 선언 포함 |
| 로컬 저장 시스템 | 예 | 아니요 | JSON 저장, 임시 파일, 백업·복구와 revision 관리 |
| 로컬 텔레메트리 | 예 | 아니요 | `user://telemetry_local.jsonl`, 런 결과와 밸런스 점검 이벤트 |
| 광고 SDK | 아니요 | 해당 없음 | provider 인터페이스만 존재. 릴리스에 provider 없음 |
| 분석 SDK | 아니요 | 해당 없음 | Firebase Analytics 등 미포함 |
| 충돌 보고 SDK | 아니요 | 해당 없음 | Crashlytics, Sentry 등 미포함 |
| 계정/로그인 SDK | 아니요 | 해당 없음 | 계정 및 인증 없음 |
| 클라우드 저장 | 아니요 | 해당 없음 | 개발자 서버 없음 |
| 인앱 결제 SDK | 아니요 | 해당 없음 | 로컬 mock 구매는 debug/demo에서만 허용 |
| 소셜/공유 SDK | 아니요 | 해당 없음 | Game Center 등 entitlement 비활성화 |

## 로컬 데이터 범주

- 가상 재화와 메타 진행
- 해금, 장비, 스티커북과 최고 기록
- 설정과 접근성 선택
- 런 결과, 보상형 기능 사용 횟수와 로컬 이벤트
- 구매 scaffold의 로컬 배열(실제 릴리스 거래 증거로 사용하지 않음)

## 권한 및 네트워크

- Android `permissions/internet=false`
- 위치, 연락처, 카메라, 마이크 권한 요청 없음
- iOS 추적 false, 암호화 비면제 사용 false
- iOS Info.plist의 카메라/마이크/사진 설명 문자열은 Godot export 호환 설정이지만 관련 API 호출과 권한 요청 없음

## 출시 때마다 확인

1. 최종 AAB/IPA에 새 SDK, native plugin 또는 네트워크 코드가 없는지 확인한다.
2. Android manifest 권한과 iOS entitlements/PrivacyInfo를 추출해 확인한다.
3. 광고 provider 또는 구매 provider가 연결됐는지 확인한다.
4. 스토어 신고와 공개 방침의 내용이 최종 바이너리와 같은지 확인한다.
5. SDK 추가 시 SDK 공급자의 데이터 공개 문서와 실제 설정을 별도로 기록한다.
