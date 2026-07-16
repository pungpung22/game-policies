# Tide Paws consent flow

## Required advertising flow

1. Request fresh UMP consent information on every mobile launch.
2. Load and present a required privacy message configured in AdMob.
3. Request/load ads only after the SDK reports that ads may be requested.
4. If consent update or form loading fails and no usable prior decision exists,
   keep ads unavailable; gameplay and purchases must remain usable.
5. When UMP requires a privacy-options entry point, expose `광고 개인정보 설정`
   in Settings and reopen the form on request.
6. Grant a rewarded benefit only from the SDK reward callback, with the existing
   daily cap and cooldown ledger preventing duplicate claims.
7. Keep purchase verification and local gameplay independent from ad consent.

## Current implementation status on 2026-07-14

- `AdsService.gd` initializes ads only when UMP reports `NOT_REQUIRED` or
  `OBTAINED`; unknown/required/error states leave rewarded ads unavailable.
- Settings exposes an ad privacy entry point plus public privacy and support links.
- The production iOS AdMob app id and one opt-in rewarded unit are configured.
- AdMob regional privacy messages still require owner-console configuration and
  physical-device QA before submission.

The remaining console configuration and device checks are App Review release
gates, not merely documentation tasks.

## ATT and children

- Current build does not request ATT and declares tracking false.
- If future AdMob configuration uses tracking, add ATT before that behavior and
  update the public policy and App Store labels.
- Decide and document the target audience. If the app is child-directed or has
  users below the applicable age, configure AdMob child treatment and consent
  behavior accordingly before requesting ads.

## Device QA

- Test EEA/UK consent-required, US-state-message and consent-not-required paths.
- Test first launch, changed decision, no network and SDK error paths.
- Test privacy-options reopening and app restart persistence.
- Confirm no reward on dismiss/failure and exactly one reward on completion.
- Generate Xcode Privacy Report from the final archive and compare disclosures.
