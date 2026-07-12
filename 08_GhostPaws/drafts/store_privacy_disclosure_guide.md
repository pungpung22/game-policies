# Ghost Paws 스토어 개인정보 신고 가이드

기준 빌드: 광고·분석·충돌 보고·로그인·클라우드·실제 결제 SDK가 없는 `com.pungpung22.ghostpaws`

## Apple App Store Connect

- Privacy Policy URL: `https://pungpung22.github.io/game-policies/08_GhostPaws/privacy/`
- Support URL: `https://pungpung22.github.io/game-policies/08_GhostPaws/support/`
- Data Collection: **No, we do not collect data from this app**
- Tracking: **No**
- IDFA/ATT: 사용 안 함, ATT 프롬프트 없음
- 계정 삭제 URL: 계정 생성 기능이 없으므로 해당 없음
- 암호화: 앱 설정상 비면제 암호화 미사용

Godot PrivacyInfo의 required-reason API 선언은 운영체제 API 사용 이유를 밝히는 것이며, 그 자체로 사용자 데이터 수집을 의미하지 않는다. 최종 archive의 PrivacyInfo와 포함 SDK를 제출 직전에 다시 확인한다.

## Google Play Console Data safety

- 앱이 필수 데이터 유형을 수집하거나 공유하는가: **아니요**
- 전송 중 암호화: 전송하는 사용자 데이터가 없음
- 데이터 삭제 요청: 계정·서버 데이터 없음. 로컬 삭제 방법을 개인정보처리방침에 안내
- 독립 보안 검토: 완료하지 않았다면 아니요
- Ads declaration: 현재 광고 SDK/광고 노출이 없으므로 **광고 없음**
- App access: 로그인 없음, 모든 기능 접근 가능

로컬에서만 처리되고 기기 밖으로 전송되지 않는 진행·설정 데이터는 현재 Data safety의 수집 항목으로 신고하지 않는다.

## 제출 전 중단 조건

다음 중 하나라도 확인되면 위 답변을 그대로 제출하지 않는다.

- 광고 또는 mediation SDK 포함
- 분석, 충돌 보고, 원격 설정, 푸시 SDK 포함
- 서버 API, 계정, 클라우드 저장 또는 리더보드 포함
- 실제 인앱 결제와 서버 영수증 검증 포함
- 지원 기능이 이메일, 로그, 첨부파일을 앱에서 자동 전송
- 인터넷/위치/카메라/마이크/사진/연락처/추적 권한 추가

변경이 있으면 SDK 데이터 목록, 개인정보처리방침, Apple App Privacy, Google Data safety, 동의 흐름과 앱 내부 고지를 함께 갱신한다.
