# Pengudoku consent flow

## Advertising consent

1. On mobile launch, request the latest UMP consent information.
2. If consent is required and a form is available, show the form.
3. Initialize and load AdMob only when the resulting UMP status allows ads.
4. If the update or form fails and no usable prior status exists, keep ads unavailable.
5. When UMP exposes privacy options, show `광고 개인정보 설정` in game settings so
   the user can reopen the form.
6. Do not grant rewarded currency or items until the SDK confirms the reward event.

## Optional analytics and crash reporting

1. Default `분석·오류 보고` to off for a new installation.
2. Keep Firebase Analytics and Crashlytics collection disabled while off.
3. Enable both only after the user switches the setting on.
4. Disable both when the user switches it off again.
5. Keep ad consent independent from the analytics/crash setting.
6. Do not assign a name, email or developer-defined user ID to Firebase.

## Release checks

- Test first launch in consent-required and consent-not-required regions.
- Test ad-unavailable behavior and reward idempotency.
- Test reopening privacy options from settings.
- Verify ATT is not requested by the shipped iOS build.
- Reconcile public policy, App Store privacy labels and Google Play Data safety answers.
