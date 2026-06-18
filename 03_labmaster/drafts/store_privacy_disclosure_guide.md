# Store Privacy Disclosure Guide

Last updated: June 18, 2026

This is a working guide for filling Google Play Data safety and Apple App Privacy. It is not a substitute for checking the final exported build and SDK privacy manifests.

Official references:

- Apple App Privacy Details: https://developer.apple.com/app-store/app-privacy-details/
- Apple User Privacy and Data Use: https://developer.apple.com/app-store/user-privacy-and-data-use/
- Apple App Store Connect privacy management: https://developer.apple.com/help/app-store-connect/manage-app-information/manage-app-privacy/
- Google Play Data safety: https://support.google.com/googleplay/android-developer/answer/10787469
- Google AdMob UMP setup: https://developers.google.com/admob/android/privacy
- Google AdMob UMP overview: https://support.google.com/admob/answer/10113005

## Google Play Data Safety Draft

Use these as starting answers if the release build contains Google Mobile Ads and platform billing.

### Does the app collect or share user data?

Draft answer: Yes, because the ad SDK and billing flow may process data.

### Data categories likely to disclose

| Google Play category | Collected? | Shared? | Purpose | Notes |
| --- | --- | --- | --- | --- |
| Location: Approximate location | Likely yes via IP-based estimate | Yes, by ad SDK | Advertising, analytics, fraud prevention | The app does not request precise location permission. |
| App activity: App interactions | Yes | Yes, by ad SDK | Advertising, analytics, fraud prevention | Includes app launches, taps, video views, ad interactions. |
| App info and performance: Diagnostics | Yes | Yes, by ad SDK | Analytics, fraud prevention, app/SDK performance | Ad SDK may collect launch time, hang rate, energy usage, errors. |
| Device or other IDs | Yes if ad SDK uses identifiers | Yes, by ad SDK | Advertising, analytics, fraud prevention | Advertising ID/device identifiers where available and permitted. |
| Financial info: Purchase history | Yes if billing is enabled | Shared with Google Play Billing | App functionality, fraud prevention | App processes product IDs/tokens/entitlements, not card data. |

### Security practices

Draft answers:

- Data is encrypted in transit: Yes for major platform SDK traffic, but verify final SDK docs.
- Users can request data deletion: App has no account or server-side save. Local save can be reset by clearing app data or uninstalling. Provide support email for requests.
- Data collection required or optional: Gameplay save is required for app functionality. Rewarded ads are optional. Personalized ads remain disabled until native consent is complete.

## Apple App Privacy Draft

Use these as starting answers if the release build contains Google Mobile Ads and StoreKit.

### Data Used To Track You

Draft answer: No for the current app flow, because personalized ads are locked and tracking should not be enabled until UMP/ATT is implemented. Revisit if production ads, mediation, or analytics use tracking.

### Data Linked To You

Potential categories to verify:

- Purchases / purchase history if StoreKit transactions are exposed to the app and linked to Apple account context by Apple.
- Identifiers if an SDK links device IDs to the user or uses them for tracking.

### Data Not Linked To You

Potential categories to verify:

- Product interaction / app interactions from ad SDK.
- Diagnostics from ad SDK or platform SDKs.
- Approximate location inferred by IP address from ad SDK.

## Production Submission Gates

- Host public Privacy Policy and Terms URLs:
  - Privacy Policy: `https://pungpung22.github.io/labmaster-policy/privacy/`
  - Terms of Service: `https://pungpung22.github.io/labmaster-policy/terms/`
  - Support: `https://pungpung22.github.io/labmaster-policy/support/`
- Fill App Store Connect App Privacy for the exact iOS archive.
- Fill Google Play Data safety for the exact Android release.
- Keep personalized ads disabled or integrate Google UMP and iOS ATT first.
- Do not submit with Google test ad IDs as production ad IDs.
- Create all App Store and Google Play IAP products before purchase QA.
