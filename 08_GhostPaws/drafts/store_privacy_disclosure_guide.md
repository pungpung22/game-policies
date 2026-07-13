# Ghost Paws 스토어 개인정보 신고 가이드

기준일: 2026년 7월 13일
앱: `com.pungpung22.ghostpaws` / 개발자: `pungpungstudi`

## 공통

- Privacy Policy: `https://pungpung22.github.io/game-policies/08_GhostPaws/privacy/`
- Support: `https://pungpung22.github.io/game-policies/08_GhostPaws/support/`
- 광고: 상점 선택형 보상 광고 1개, 20개/회, UTC 기준 하루 3회
- 배너/전면/앱 시작/강제 부활/리롤 광고 없음
- 계정, 분석 SDK, 클라우드, 채팅, UGC 없음
- Google Mobile Ads/UMP의 실제 최종 버전과 설정에서 양식을 작성한다.

## Apple App Store Connect

- App Privacy에서 IP 주소 기반 대략적 위치, 기기 ID, 광고 데이터, 제품
  상호작용, 충돌/진단 및 성능 데이터를 Google의 최신 iOS 공개 문서와 대조한다.
- 목적은 Third-Party Advertising, Developer's Advertising or Marketing,
  Analytics, App Functionality/Fraud Prevention 중 실제 SDK 보고서에 맞게 선택한다.
- 현재 Tracking은 `No`로 계획하며 ATT 프롬프트를 요청하지 않는다. 최종 Xcode
  privacy report에서 SDK의 tracking domain/IDFA 사용을 다시 확인한다.
- Account deletion URL은 계정 기능이 없어 해당 없음이다.
- StoreKit provider가 추가되면 Purchases와 product/transaction ID 처리를 재검토한다.

## Google Play Console

- Ads declaration: **Yes**
- Data safety에서 기존 `수집 없음/공유 없음` 답변을 사용하지 않는다.
- Google Mobile Ads Android 공개 문서에 따라 IP 주소, 앱/광고 상호작용,
  진단, 기기·계정 식별자의 수집/공유 및 광고·분석·부정행위 방지 목적을 검토한다.
- Google SDK 전송은 TLS 암호화로 안내되어 있으나 최종 양식은 계정 소유자가 확인한다.
- Account creation: 없음. 로컬 데이터는 앱 저장공간 삭제/제거로 삭제한다.
- 최종 AAB의 `INTERNET`, `ACCESS_NETWORK_STATE`, `AD_ID` 및 간접 SDK를 확인한다.
- 대상 연령에 아동이 포함되면 Families용 광고 SDK/콘텐츠/개인 맞춤 설정 요건을
  별도로 충족한 뒤 제출한다.

## 제출 중단 조건

- Google 테스트 App ID/광고 단위 ID가 남아 있음
- AdMob Privacy & messaging 양식 미게시
- 공개 루트 `app-ads.txt`의 게시자 행 확인 실패
- 최종 AAB/IPA와 정책의 SDK 버전 또는 데이터 범주가 다름
- mediation, 분석, 충돌 보고, 푸시, 계정, 서버, IAP provider가 문서 갱신 없이 추가됨
