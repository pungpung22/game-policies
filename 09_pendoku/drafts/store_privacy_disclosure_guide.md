# Pengudoku store privacy disclosure guide

This is a release checklist, not the public privacy policy. Reconfirm every answer in
App Store Connect and Google Play Console against the exact submitted binaries.

## Data handled by the app or SDKs

| Category | Default behavior | Purpose | Linked to identity |
| --- | --- | --- | --- |
| Local gameplay/progress | Stored on device | App functionality | No account |
| Advertising identifiers and interactions | AdMob/UMP may process | Third-party advertising, measurement, fraud prevention | Review Google SDK definition |
| IP address/coarse location | AdMob and enabled Firebase may infer/process | Ads, analytics, security | Review platform definition |
| Product interaction | Firebase only after user opt-in; AdMob for ad interactions | Analytics, ads | No developer-set user ID |
| Crash/performance diagnostics | Firebase only after user opt-in; ad SDK may process its diagnostics | App functionality, analytics, ads | No developer-set user ID |
| Purchase and transaction identifiers | Store billing | App functionality, purchase fulfillment | Store account controls linkage |

## App Store Connect review points

- Account/contact information: not collected by the app.
- Purchases: store handles payment; the app receives product and transaction state.
- Identifiers, usage and diagnostics: disclose according to current AdMob and Firebase SDK labels.
- Tracking: the app does not request ATT or intentionally use IDFA without permission.
  Recheck AdMob configuration and Apple definitions before answering “Data Used to Track You.”
- Analytics/Crashlytics: off by default and only enabled by the in-app user setting.
- Privacy Policy URL: `https://pungpung22.github.io/game-policies/09_pendoku/privacy/`

## Google Play Data safety review points

- AdMob/UMP may collect and share device or other identifiers, coarse location, app
  interactions, advertising data and diagnostics for advertising, analytics, security
  and fraud prevention.
- Firebase Analytics/Crashlytics collection is optional and disabled by default.
- Purchase information is handled through Google Play Billing when Android billing is enabled.
- Data is encrypted in transit by the SDK providers.
- Users can delete local app data by clearing storage or uninstalling.
- No account deletion flow is required because the game has no account system.

## Not requested by the game

Camera, microphone, contacts, photos, precise location, health, messages, address book,
user-generated content and developer-operated cloud save.
