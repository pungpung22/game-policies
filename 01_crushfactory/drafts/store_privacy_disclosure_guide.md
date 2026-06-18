# Store Privacy Disclosure Guide

Last updated: June 18, 2026

This is a working guide for filling Google Play Data safety and Apple App Privacy. It is not a substitute for checking the final exported build and SDK privacy manifests.

Official references checked:

- Google Play Data safety: https://support.google.com/googleplay/android-developer/answer/10787469
- Google AdMob Android data disclosure: https://developers.google.com/admob/android/privacy/play-data-disclosure
- Google AdMob iOS data disclosure: https://developers.google.com/admob/ios/privacy/data-disclosure
- Apple App Privacy Details: https://developer.apple.com/app-store/app-privacy-details/
- Apple App Review Guidelines: https://developer.apple.com/app-store/review/guidelines/
- Apple User Privacy and Data Use: https://developer.apple.com/app-store/user-privacy-and-data-use/

## Google Play Data Safety Draft

Use these as starting answers if the release build contains Google Mobile Ads rewarded ads and platform billing.

### Does the app collect or share user data?

Draft answer: Yes, because the ad SDK and billing flow process data.

### Data categories likely to disclose

| Google Play category | Collected? | Shared? | Purpose | Notes |
| --- | --- | --- | --- | --- |
| Location: Approximate location | Likely yes via IP-based estimate | Yes, by ad SDK | Advertising, analytics, fraud prevention | The app does not request precise location permission. |
| App activity: App interactions | Yes | Yes, by ad SDK | Advertising, analytics, fraud prevention | Includes app launches, taps, video views, ad interactions. |
| App info and performance: Diagnostics | Yes | Yes, by ad SDK | Analytics, fraud prevention, app/SDK performance | Ad SDK may collect launch time, hang rate, energy usage, errors. |
| Device or other IDs | Yes | Yes, by ad SDK | Advertising, analytics, fraud prevention | Advertising ID/device identifiers where available and allowed. |
| Financial info: Purchase history | Yes if billing is enabled | Shared with Google Play Billing | App functionality, fraud prevention | App should process product IDs/tokens/entitlements, not card data. |

### Security practices

Draft answers:

- Data is encrypted in transit: Yes for major platform SDK traffic, but verify final SDK docs.
- Users can request data deletion: App has no account or server-side save. Local save can be reset in Settings or removed by uninstalling. Provide support email for requests.
- Data collection required or optional: Gameplay save is required for app functionality. Rewarded ads are optional. Tracking/personalized ads depend on consent where required.

### Google Play notes

- Privacy Policy URL is required before submission.
- Data safety answers must include SDK behavior, not just first-party app code.
- Do not claim "no data collected" if AdMob is enabled.

## Apple App Privacy Draft

Use these as starting answers if iOS release includes Google Mobile Ads and StoreKit.

### Data Used to Track You

Possible: Yes, if IDFA or other data is used for tracking across apps/websites by ad partners. If ATT is denied and only non-tracking contextual ads are served, verify with SDK settings before answering.

Likely data types to review:

- Identifiers: Device ID / Advertising ID
- Usage Data: Product Interaction / Advertising Data

### Data Linked to You

Ad SDKs and StoreKit may link some data to device identifiers, purchase records, or advertising identifiers depending on configuration.

Likely data types to review:

- Purchases: Purchase History
- Identifiers: Device ID
- Usage Data: Product Interaction / Advertising Data
- Diagnostics: Crash Data / Performance Data if SDK privacy manifest reports it

### Data Not Linked to You

Some diagnostics or aggregated ad metrics may be reported as not linked depending on SDK privacy manifests. Verify in Xcode/App Store Connect privacy reports.

### Apple notes

- App Privacy answers must include third-party partner collection.
- If tracking is used, App Tracking Transparency must be shown before tracking.
- Do not gate gameplay, purchases, or rewards on accepting tracking.

## Store Listing Disclosure Copy

Short app store disclosure:

Crush Factory contains optional rewarded ads and in-app purchases. In-game currency and items have no real-world cash value. Ads and purchases are used only for gameplay rewards and progression.

Remove-ads disclosure:

Clean Factory Pass removes forced/interstitial ads where those ads are enabled. Optional rewarded bonuses may remain available as ad-free equivalent claims when supported.

Children/family positioning:

Crush Factory is not intended for children under 13 and should not be submitted to Google Play Families or Apple Kids Category unless the ad SDK settings, content rating, privacy policy, and purchase flow are rebuilt for child-directed treatment.

